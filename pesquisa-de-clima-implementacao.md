# Pesquisa de Clima — Implementação Técnica

> "Documentar o que só você sabe tem que virar texto antes de ele sair."
> Este arquivo é o runbook do formulário: como foi criado, como recriar e como migrar.

Registro técnico da criação do Google Forms da [Pesquisa de Clima](pesquisa-de-clima.md).
Quem ler isto consegue recriar o formulário do zero sem perguntar nada.

---

## Contexto

A pesquisa exige **Google Forms anônimo** (sem nome, sem e-mail, sem login).
A criação manual no Forms é frágil — labels de escala erram fácil e o anonimato vem desligado por padrão em contas Workspace.

Solução: criar via **Google Apps Script**, versionado neste repositório. Roda em 1 minuto e sai idêntico ao playbook toda vez.

---

## Formulário Ativo

| Item | Link |
|------|------|
| Editar (admin) | https://docs.google.com/forms/d/1MzjGN2IKctDgbWl_CU1S1DJdKQAhuL4MPm2-Pfu0yjQ/edit |
| Responder (enviar p/ colaboradores) | https://docs.google.com/forms/d/e/1FAIpQLSfSprQEbIPFxXRXG14CNJmEUw0S3wrRAmalKOgnMjJjaXhr1Q/viewform |

**Conta proprietária atual:** `neriton.santos@gmail.com` (provisória — criado para teste em 29/05/2026)
**Conta de destino:** `operacoes@mirandas.com.br` (recriar lá antes do disparo oficial — ver seção Migração)

---

## Configuração de Anonimato

Garantido via script e validado nas configurações do form:

- [x] `setCollectEmail(false)` — não coleta e-mail
- [x] `setLimitOneResponsePerUser(false)` — não exige login Google
- [x] Sem campo de nome em nenhuma pergunta
- [x] Sem restrição de domínio (qualquer pessoa com o link responde)
- [ ] **Conferir no Workspace:** se recriado em `operacoes@mirandas.com.br`, verificar nas Configurações se "Restringir a usuários de Grupo Mirandas" está **desligado** — senão quebra o anonimato e bloqueia quem é de fora.

---

## Mapeamento das Perguntas

| # | Bloco | Pergunta | Tipo | Escala (1 → 5) |
|---|-------|----------|------|----------------|
| 1 | Clareza | Entende o que é esperado de você | Escala 1–5 | Não tenho clareza nenhuma → Total clareza |
| 2 | Clareza | Conecta seu trabalho à missão (100.000 famílias) | Escala 1–5 | Não vejo conexão → Vejo claramente |
| 3 | Clareza | O que poderia ser mais claro hoje | Campo aberto | — |
| 4 | Liderança | Líder direto te dá suporte pra performar | Escala 1–5 | Nunca → Sempre |
| 5 | Liderança | À vontade pra trazer problema pro líder | Escala 1–5 | Jamais → Totalmente |
| 6 | Liderança | Algo na liderança que, se mudasse, ajudaria | Campo aberto | — |
| 7 | Pertencimento | Recomendaria o Grupo Mirandas como lugar pra trabalhar | Escala 1–5 | Jamais → Com certeza |
| 8 | Pertencimento | Nível de energia e disposição (últimos 30 dias) | Escala 1–5 | Esgotado → Muito bem |
| 9 | Pertencimento | Uma coisa que mudaria na empresa | Campo aberto | — |

Escalas: **obrigatórias**. Campos abertos: **opcionais**.

---

## Script de Criação (Apps Script)

> Fonte da verdade. Para recriar, cole em [script.google.com](https://script.google.com) → Executar → autorizar.
> Os links de edição e resposta aparecem em **Visualizar → Logs** (Ctrl+Enter).

```javascript
function criarPesquisaClima() {
  var form = FormApp.create('Pesquisa de Clima — Grupo Mirandas');

  form.setDescription(
    '"Você não pode melhorar o que não mede. Clima é o termômetro do turnover."\n\n' +
    'Pesquisa trimestral ANÔNIMA. Tempo médio: 5 minutos.\n' +
    'Sem nome, sem e-mail, sem identificação. Suas respostas nunca são usadas para punição individual — é dado de processo.\n' +
    'Seja honesto: é exatamente por isso que essa pesquisa existe.'
  );

  // ---- Configuração de anonimato ----
  form.setCollectEmail(false);            // não coleta e-mail
  form.setLimitOneResponsePerUser(false); // não exige login Google
  form.setProgressBar(true);
  form.setConfirmationMessage('Obrigado. Sua resposta foi registrada de forma anônima. 💚');

  // ===== BLOCO 1 — CLAREZA =====
  form.addSectionHeaderItem()
    .setTitle('Bloco 1 — Clareza')
    .setHelpText('Você sabe o que se espera de você e por quê.');

  form.addScaleItem()
    .setTitle('Você entende claramente o que é esperado de você no seu trabalho?')
    .setBounds(1, 5)
    .setLabels('Não tenho clareza nenhuma', 'Total clareza')
    .setRequired(true);

  form.addScaleItem()
    .setTitle('Você consegue conectar o seu trabalho com a missão da empresa (100.000 famílias)?')
    .setBounds(1, 5)
    .setLabels('Não vejo conexão', 'Vejo claramente')
    .setRequired(true);

  form.addParagraphTextItem()
    .setTitle('O que poderia ser mais claro pra você hoje — processo, expectativa ou direção?')
    .setRequired(false);

  // ===== BLOCO 2 — LIDERANÇA =====
  form.addSectionHeaderItem()
    .setTitle('Bloco 2 — Liderança')
    .setHelpText('Você se sente apoiado e bem liderado.');

  form.addScaleItem()
    .setTitle('Seu líder direto te dá o suporte que você precisa pra performar?')
    .setBounds(1, 5)
    .setLabels('Nunca', 'Sempre')
    .setRequired(true);

  form.addScaleItem()
    .setTitle('Você se sente à vontade pra trazer um problema ou dificuldade pro seu líder?')
    .setBounds(1, 5)
    .setLabels('Jamais', 'Totalmente')
    .setRequired(true);

  form.addParagraphTextItem()
    .setTitle('Tem algo na liderança que, se mudasse, te ajudaria a trabalhar melhor?')
    .setRequired(false);

  // ===== BLOCO 3 — PERTENCIMENTO =====
  form.addSectionHeaderItem()
    .setTitle('Bloco 3 — Pertencimento')
    .setHelpText('Você quer continuar aqui e sente que vale a pena.');

  form.addScaleItem()
    .setTitle('Você recomendaria o Grupo Mirandas como um bom lugar pra trabalhar?')
    .setBounds(1, 5)
    .setLabels('Jamais', 'Com certeza')
    .setRequired(true);

  form.addScaleItem()
    .setTitle('Como você avalia seu nível de energia e disposição no trabalho nos últimos 30 dias?')
    .setBounds(1, 5)
    .setLabels('Esgotado', 'Muito bem')
    .setRequired(true);

  form.addParagraphTextItem()
    .setTitle('Se você pudesse mudar uma coisa na empresa, o que seria?')
    .setRequired(false);

  // ---- Links (aparecem em Visualizar > Logs) ----
  Logger.log('✏️  Editar form: ' + form.getEditUrl());
  Logger.log('🔗  Link de resposta (enviar p/ colaboradores): ' + form.getPublishedUrl());
}
```

---

## Como Recriar — Passo a Passo

> Use a cada trimestre se quiser um form novo por ciclo, ou uma única vez na conta oficial.

- [ ] Acessar [script.google.com](https://script.google.com) → **Novo projeto**
- [ ] Nomear o projeto (ex: `Pesquisa de Clima`) e salvar (Ctrl+S)
- [ ] Colar o script acima
- [ ] Confirmar que a função selecionada no topo é `criarPesquisaClima`
- [ ] **Executar** (▶) → Revisar permissões → Avançado → Acessar → **Permitir**
- [ ] Abrir **Visualizar → Logs** (Ctrl+Enter) e copiar os dois links
- [ ] Atualizar a seção **Formulário Ativo** deste arquivo com os links novos
- [ ] Disparar o link de resposta no canal definido (ver [calendário](pesquisa-de-clima.md#calendário-de-disparo))

---

## Migração para Conta Oficial

O dono do form é a conta que executa o script. O form atual está na conta pessoal.

- [ ] Logar em `operacoes@mirandas.com.br`
- [ ] Rodar o mesmo script (cria form novo, zerado, sob a conta oficial) — **preferível à transferência de propriedade**
- [ ] Conferir anonimato (seção Configuração de Anonimato — atenção à restrição de domínio Workspace)
- [ ] Substituir os links na seção **Formulário Ativo**
- [ ] Arquivar/descartar o form da conta pessoal

---

## Próximos Passos — Relatório Automático

O playbook prevê relatório trimestral automático (Carla → Anthony) com média por bloco, status 🟢🟡🔴 e alertas <3.5. **Ainda não implementado.**

Caminho técnico sugerido (Apps Script + planilha de respostas):
- [ ] Vincular respostas a uma Planilha (Forms → Respostas → vincular ao Sheets)
- [ ] Script que calcula média por bloco e delta vs. trimestre anterior
- [ ] Disparo de alerta (e-mail/WhatsApp) quando qualquer bloco < 3.5
- [ ] Validação de quórum: relatório só vale com ≥70% de resposta

---

## Papéis

| Quem | Responsabilidade |
|------|-----------------|
| Neriton | Criar/recriar o form, manter o script versionado, migrar para conta oficial |
| Carla | Disparo do link, curadoria das respostas abertas, relatório trimestral |
| Anthony | Recebe relatório e alertas <3.5 |

---

*Última atualização: 29/05/2026 — formulário criado via Apps Script na conta neriton.santos@gmail.com (provisória)*
