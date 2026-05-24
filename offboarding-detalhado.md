# Offboarding Detalhado — Grupo Mirandas

> Offboarding nao e despedida. E transferencia de ativos e encerramento limpo.
> Meta: no ultimo dia, todos os acessos entregues, nenhum processo parado, zero risco juridico.

---

## REGRAS DE OURO DO OFFBOARDING

1. **Nunca avisar sem ter o checklist de acessos fechado** — primeiro mapear, depois comunicar.
2. **Transferencia de acesso antes de ultimo dia** — nunca depender de boa vontade pos-encerramento.
3. **Documentar o que so ele sabe** — cada processo critico vira runbook antes de sair.
4. **Pagamento final so apos confirmacao de entrega** — cláusula contratual te protege.
5. **Tom respeitoso e direto** — nao e demissao emocional, e decisao de negocio.
6. **Comunicacao interna antes da externa** — time sabe antes de qualquer anuncio publico.

---

## TIMELINE PADRAO (contrato PJ — 30 dias de aviso)

| Dia | Marco | Responsavel |
|-----|-------|-------------|
| D0 | Decisao interna tomada | Anthony |
| D0 | Mapear acessos que ele tem | Carla |
| D1 | Conversa de comunicado (aviso formal) | Anthony |
| D1–D7 | Entrega de acessos criticos (primeira rodada) | Colaborador + Neriton |
| D7 | Checar se todos os acessos criticos foram entregues | Neriton |
| D7–D21 | Documentacao de processos que so ele sabe | Colaborador |
| D21 | Review do material documentado | Anthony ou Lider direto |
| D25 | Entrega final de acessos remanescentes | Colaborador + Neriton |
| D28 | Confirmacao de que nao ha pendencias | Carla |
| D30 | Ultimo dia — desativacao de todos os acessos | Neriton |
| D30 | Pagamento proporcional final | Edwards/Midiane |
| D31 | Acessos desativados e verificados | Neriton |

---

## D0 — ANTES DE COMUNICAR

**Nao avisar antes de ter isso mapeado.**

### Checklist pre-comunicado

- [ ] Contrato relido — entender prazo de aviso, multa (se houver), clausula de entrega de acessos
- [ ] Lista completa de acessos que ele possui (ver secao Acessos abaixo)
- [ ] Quem assume cada responsabilidade durante os 30 dias
- [ ] Quem assume permanentemente apos o desligamento
- [ ] Processos criticos que so ele executa (mapear antes)
- [ ] Pagamento final calculado (proporcional + variavel ate data)
- [ ] Comunicacao interna planejada (quem sabe antes, quem sabe depois)

---

## D1 — CONVERSA DE COMUNICADO

### Script da conversa (adaptavel por perfil DISC)

**Abertura direta (nao criar suspense):**
> "Ralph, vou ser direto: decidimos encerrar nossa parceria. O contrato prevê 30 dias de aviso — o ultimo dia sera [DATA]. Voce segue recebendo normalmente durante esse periodo."

**Explicacao (1 frase, sem drama):**
> "A empresa esta mudando a estrutura do Growth. Nao e sobre performance pessoal — e sobre o que o negocio precisa agora."

**Proximo passo imediato (assumir o controle do processo):**
> "Vou te passar uma lista de acessos que preciso que voce transfira ainda essa semana. Neriton vai te contatar para coordenar a parte tecnica."

**Encerrar:**
> "Quer fazer perguntas agora ou prefere processar e falar amanha?"

### O que NAO fazer na conversa
- Nao negociar prazo na hora — diga que precisa verificar antes de responder qualquer pedido
- Nao explicar mais do que o necessario — quanto mais voce explica, mais abre para debate
- Nao prometer carta de recomendacao no mesmo dia — avalie antes
- Nao deixar a conversa sem proximo passo claro definido

---

## CHECKLIST DE ACESSOS — HEAD GROWTH

> Adaptar para cada cargo. Esta lista e especifica para a funcao de Head Growth.

### Meta Ads (CRITICO — transferir em D1-D3)
- [ ] Gerenciador de Negocios — remover acesso admin ou transferir propriedade
- [ ] Conta Yes Consorcio `act_1156743682306754` — verificar acesso
- [ ] Conta Anthony `act_663271449065418` — verificar acesso
- [ ] Pixels instalados nos sites — documentar IDs
- [ ] Publicos personalizados e lookalikes — exportar lista e documentar logica
- [ ] Bibliotecas de criativos — exportar ou garantir acesso permanente

### Email / Automacao (CRITICO)
- [ ] Brevo — transferir acesso admin, documentar listas, fluxos e templates ativos
- [ ] Domínios de envio configurados — documentar DNS e configuracoes SPF/DKIM
- [ ] API keys em uso — revogar e recriar sob credencial da empresa

### Redes Sociais
- [ ] Instagram — confirmar que acesso esta sob conta empresa (nao conta pessoal dele)
- [ ] Facebook Page — confirmar admin primario e remover acesso dele
- [ ] YouTube — confirmar gerenciamento via conta empresa

### Sites e Funis
- [ ] Funis em producao — documentar estrutura e onde estao hospedados
- [ ] WordPress/Elementor — credenciais de acesso e hosting
- [ ] Dominios registrados — confirmar que estao em conta da empresa (nao cpf/cnpj dele)
- [ ] Landing pages ativas — listar URLs e responsavel tecnico

### Ferramentas
- [ ] Canva Pro — exportar projetos e assets da marca; transferir ownership
- [ ] Google Analytics — remover acesso apos documentar configuracoes de propriedade
- [ ] Google Tag Manager — remover acesso apos documentar tags ativas
- [ ] Ferramentas de espionagem/analise (SpyFu, SimilarWeb, etc) — cancelar ou transferir

### Acessos Internos
- [ ] Bitrix ID 33527 — desativar perfil no ultimo dia (Neriton executa)
- [ ] GitHub OrgGrupoMirandas — remover da organizacao no ultimo dia
- [ ] Drive Grupo Mirandas — revogar acesso no ultimo dia
- [ ] Email corporativo (se houver) — configurar redirecionamento e desativar
- [ ] Senhas compartilhadas em gerenciador — revogar apos transferencia

---

## D7–D21 — DOCUMENTACAO DE PROCESSOS CRITICOS

> O que so ele sabe tem que virar texto antes de ele sair.

### O que documentar (Head Growth)

| Processo | Formato | Prazo |
|---------|---------|-------|
| Estrutura atual das campanhas ativas (Meta Ads) | Documento com screenshots + logica de segmentacao | D10 |
| Fluxos de automacao Brevo ativos | Descricao de cada fluxo, trigger e sequencia | D10 |
| CPA atual por campanha e como foi atingido | Planilha ou documento | D14 |
| Historico de testes de criativos (o que funcionou, o que nao funcionou) | Documento | D14 |
| Quais ferramentas pagas existem e para que servem | Lista com login, funcao e valor mensal | D7 |
| Contatos externos (designers, agencias, freelancers) | Lista com nome, contato, escopo e status | D7 |
| Processos manuais que ele faz todo mes | Runbook passo a passo | D21 |

### Criterio de aceite da documentacao

Quem recebe o processo consegue executar sozinho sem perguntar nada.
Se nao consegue, o documento esta incompleto — devolver para retrabalho.

---

## D28–D30 — ENCERRAMENTO

### Checklist final (Neriton executa, Carla verifica)

**Acessos:**
- [ ] Todos os itens do checklist de acessos confirmados como entregues
- [ ] Nenhum acesso ativo remanescente (verificar em cada plataforma)
- [ ] Senhas alteradas em todos os sistemas que ele tinha acesso

**Documentacao:**
- [ ] Todos os documentos previstos entregues e aprovados
- [ ] Documentos salvos na pasta correta no Drive (RH > nome do colaborador)
- [ ] Runbooks publicados no repositorio correspondente

**Financeiro:**
- [ ] Valor final calculado (fixo proporcional + variavel ate data)
- [ ] NF solicitada (contrato PJ)
- [ ] Pagamento agendado para o dia do encerramento ou dia util seguinte

**Comunicacao:**
- [ ] Time informado internamente antes do ultimo dia
- [ ] Carta de recomendacao decidida (sim ou nao — se sim, entregue)
- [ ] Mensagem de agradecimento opcional (criterio de Anthony)

---

## COMUNICACAO INTERNA

### Quem sabe antes do comunicado ao colaborador
- Ninguem alem de Anthony e Edwards (enquanto nao for comunicado)

### Quem sabe logo apos o comunicado ao colaborador
- Edwards (COO) — mesmo dia
- Lider direto da area afetada — mesmo dia
- Neriton — para preparar lista de acessos

### Quem sabe quando?
- Time geral — somente quando o proprio colaborador souber (evitar vazamento)
- Mensagem padrao para o time: "O [Nome] encerrou sua parceria com o Grupo Mirandas a partir de [DATA]. Agradecemos a contribuicao e desejamos sucesso. Para continuidade dos processos, [Nome do substituto ou redistribuicao] assume."

---

## PAPEIS NO OFFBOARDING

| Quem | Responsabilidade |
|------|-----------------|
| Anthony | Decisao, conversa de comunicado, aprovacao da documentacao |
| Edwards | Calculo e pagamento final, revisao contratual |
| Neriton | Coordenacao tecnica de acessos, desativacao no ultimo dia |
| Midiane | NF, pagamento, documentacao financeira |
| Carla | Mapear acessos pre-comunicado, acompanhar checklist, alertar atrasos |

---

## CLAUSULAS CONTRATUAIS — HEAD GROWTH (Ralph Marek)

> Referencia para conferir antes de iniciar qualquer processo.

- **Tipo:** PJ — Instrumento Particular de Prestacao de Servicos
- **Aviso previo:** 30 dias por comunicacao escrita
- **Multa rescisoria:** nenhuma (periodo de teste ja encerrado)
- **Variavel na rescisao:** proporcional ao lucro liquido apurado ate a data do encerramento
- **Nao-concorrencia:** 2 anos apos rescisao em marketing digital, cursos, mentorias, assessorias e consorcios
- **Entrega de acessos:** imediata, obrigacao contratual (clausula 2.1.1.3)
- **Propriedade intelectual:** todo codigo, sistema, agente de IA, prompt, fluxo desenvolvido durante o contrato e da CONTRATANTE (clausula 5.10)

---

## CHECKLIST GERAL — D0 ATE D31

### Pre-comunicado (D0)
- [ ] Contrato relido e clausulas mapeadas
- [ ] Lista de acessos mapeada
- [ ] Responsavel por cada processo definido
- [ ] Pagamento final calculado
- [ ] Script da conversa preparado

### Comunicado e primeira semana (D1-D7)
- [ ] Conversa realizada (D1)
- [ ] Acessos criticos entregues (D1-D3)
- [ ] Lista de ferramentas com valores recebida (D7)
- [ ] Contatos externos recebidos (D7)
- [ ] Time interno comunicado

### Documentacao (D7-D21)
- [ ] Estrutura de campanhas documentada (D10)
- [ ] Fluxos Brevo documentados (D10)
- [ ] Historico de testes documentado (D14)
- [ ] CPA por campanha documentado (D14)
- [ ] Runbooks de processos manuais entregues (D21)
- [ ] Documentacao revisada e aprovada (D21)

### Encerramento (D25-D31)
- [ ] Verificacao final de todos os acessos (D25)
- [ ] Acessos remanescentes transferidos (D25)
- [ ] Bitrix desativado (D30)
- [ ] GitHub — removido da org (D30)
- [ ] Drive — acesso revogado (D30)
- [ ] Pagamento realizado (D30)
- [ ] NF emitida e arquivada (D30)
- [ ] Verificacao final — nenhum acesso ativo (D31)
