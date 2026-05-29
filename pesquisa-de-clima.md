# Pesquisa de Clima — Grupo Mirandas

> "Você não pode melhorar o que não mede. Clima é o termômetro do turnover."

Pesquisa trimestral anônima para detectar erosão de engajamento antes que vire desligamento.

> ✅ **Formulário criado e no ar desde 29/05/2026.**
> Link para responder: https://docs.google.com/forms/d/e/1FAIpQLSfSprQEbIPFxXRXG14CNJmEUw0S3wrRAmalKOgnMjJjaXhr1Q/viewform
> Detalhes técnicos (script, como recriar) em [pesquisa-de-clima-implementacao.md](pesquisa-de-clima-implementacao.md).

---

## Contexto

T1 2026: 7 desligamentos. Padrão identificado — contratações por feeling, sem canal formal de feedback ascendente.
Solução: pesquisa trimestral com 9 perguntas, 3 blocos, resultado automatizado pra Carla.

**Frequência:** Trimestral (março, junho, setembro, dezembro)
**Canal:** Google Forms anônimo
**Tempo médio:** 5 minutos
**Responsável pelo disparo:** Carla (automação) ou Neriton (manual)
**Responsável pela análise:** Carla → relatório pra Anthony

---

## Perguntas

### Bloco 1 — Clareza
*Você sabe o que se espera de você e por quê.*

**1.** Em uma escala de 1 a 5, você entende claramente o que é esperado de você no seu trabalho?
`1 = Não tenho clareza nenhuma → 5 = Total clareza`

**2.** Em uma escala de 1 a 5, você consegue conectar o seu trabalho com a missão da empresa (100.000 famílias)?
`1 = Não vejo conexão → 5 = Vejo claramente`

**3.** O que poderia ser mais claro pra você hoje — processo, expectativa ou direção?
`(campo aberto)`

---

### Bloco 2 — Liderança
*Você se sente apoiado e bem liderado.*

**4.** Em uma escala de 1 a 5, seu líder direto te dá o suporte que você precisa pra performar?
`1 = Nunca → 5 = Sempre`

**5.** Em uma escala de 1 a 5, você se sente à vontade pra trazer um problema ou dificuldade pro seu líder?
`1 = Jamais → 5 = Totalmente`

**6.** Tem algo na liderança que, se mudasse, te ajudaria a trabalhar melhor?
`(campo aberto)`

---

### Bloco 3 — Pertencimento
*Você quer continuar aqui e sente que vale a pena.*

**7.** Em uma escala de 1 a 5, você recomendaria o Grupo Mirandas como um bom lugar pra trabalhar?
`1 = Jamais → 5 = Com certeza`

**8.** Em uma escala de 1 a 5, como você avalia seu nível de energia e disposição no trabalho nos últimos 30 dias?
`1 = Esgotado → 5 = Muito bem`

**9.** Se você pudesse mudar uma coisa na empresa, o que seria?
`(campo aberto)`

---

## Output — Relatório Trimestral (Carla → Anthony)

Após cada ciclo, relatório automático com:

| Bloco | Média | Status |
|-------|-------|--------|
| Clareza | X.X / 5 | 🟢 / 🟡 / 🔴 |
| Liderança | X.X / 5 | 🟢 / 🟡 / 🔴 |
| Pertencimento | X.X / 5 | 🟢 / 🟡 / 🔴 |

**Alertas automáticos:**
- Qualquer bloco < 3.5 → alerta imediato pra Anthony
- Queda de 0.5+ em relação ao trimestre anterior → flag de atenção
- Respostas abertas agrupadas por tema (Carla faz curadoria)

**Comparativo:** sempre exibir delta vs trimestre anterior.

---

## Calendário de Disparo

| Trimestre | Disparo | Prazo resposta | Relatório |
|-----------|---------|----------------|-----------|
| T1 | 1º março | 7 março | 8 março |
| T2 | 1º junho | 7 junho | 8 junho |
| T3 | 1º setembro | 7 setembro | 8 setembro |
| T4 | 1º dezembro | 7 dezembro | 8 dezembro |

---

## Regras

- **Anônima de verdade** — sem campo de nome, sem e-mail obrigatório, sem IP logging
- **Todo colaborador ativo** recebe o link (não só liderança)
- **Mínimo 70% de resposta** pra relatório ser válido — abaixo disso, Carla re-dispara com lembrete
- Resultado **nunca é usado pra punição individual** — é dado de processo

---

*Última atualização: 25/05/2026 — baseado nos padrões de desligamento T1 2026*
