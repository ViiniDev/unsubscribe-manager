# Pesquisa de Concorrentes

> Fase 01 — Discovery · Status: concluído · Consulta às fontes: 2026-11-24
>
> Levantamento de ferramentas existentes a partir de fontes públicas. **Não é pesquisa de mercado com usuários.**

## Panorama

| Ferramenta | O que faz | Modelo | Observação |
|---|---|---|---|
| Gmail — "Gerenciar inscrições" | Lista nativa de inscrições ordenada por frequência, com cancelamento em um clique | Gratuito | Agrupa por **remetente**; liberação gradual por país/conta |
| Unroll.me | Cancelamento em massa | Gratuito | Caso conhecido de privacidade: dados de caixas de entrada usados comercialmente pela controladora; acordo com a FTC em 2019 |
| Clean Email | Limpeza ampla da caixa + Unsubscriber | Pago | Também move para a lixeira e-mails de listas que ignoram o cancelamento |
| Leave Me Alone | Cancelamento com foco em privacidade | Pago/freemium | Requer acesso amplo à caixa de entrada |
| Inbox Zero | Assistente de e-mail com recurso de cancelamento em massa | Assinatura ou self-host | Open source; escopo muito maior que cancelamento |
| Gmail Cleaner | Cancelamento em massa executado localmente | Gratuito | Open source; proposta parecida com a deste projeto |

## Teste do recurso nativo do Gmail (evidência própria)

Ao usar o "Gerenciar inscrições", senti falta de uma **descrição do tipo de conteúdo** enviado por cada inscrição. Remetentes aparecem apenas pelo nome (ex.: uma faculdade, companhias aéreas), sem indicar se enviam promoções, comunicados ou mensagens transacionais. Isso dificulta decidir o que cancelar, especialmente quando um mesmo remetente envia tanto promoções quanto mensagens importantes (ex.: confirmação de passagem).

## Conclusões

- **Ser local e open source não é um diferencial exclusivo**: já existem projetos assim. É, porém, um atributo de qualidade (privacidade e auditabilidade).
- **Diferenciais pretendidos** (hipótese H3, não verificada em todos os concorrentes):
  - mostrar **o que cada lista realmente envia** (amostra de assuntos);
  - **categorias protegidas** por regra e decisão manual para vagas;
  - **status honesto**: "solicitado" não é o mesmo que "confirmado";
  - agrupamento por **lista** (`List-ID`), não apenas por remetente.

## Fontes

- Google — Gerenciar inscrições no Gmail: https://support.google.com/mail/answer/15621070
- Google Blog — Manage subscriptions (jul/2025): https://blog.google/products/gmail/new-manage-subscriptions-unsubscribe/
- FTC — acordo com Unroll.me: https://www.ftc.gov/node/48064
- Clean Email — Unsubscriber: https://clean.email/unsubscriber
- Leave Me Alone: https://leavemealone.com/
- Inbox Zero (GitHub): https://github.com/elie222/inbox-zero
- Gmail Cleaner: https://gururagavendra.github.io/gmail-cleaner
