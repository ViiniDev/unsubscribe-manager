# Visão e Escopo do Projeto

> Fase 01 — Discovery · Status: concluído · Data: 2026-11-24

## Proposta de valor

> Um gerenciador de inscrições do Gmail, **local e open source**, que mostra **o que cada lista realmente envia** e cancela em lote só o que é seguro, protegendo e-mails críticos e deixando decisões sensíveis com você.

## Visão

O Unsubscribe Manager é uma aplicação local que se conecta à conta Gmail do usuário, identifica as listas de e-mail recebidas, mostra o que cada uma envia e permite cancelar inscrições em lote com segurança. E-mails críticos ficam protegidos e o resultado de cada solicitação é reportado com transparência.

**Objetivos:** resolver um problema real do autor e aprofundar o aprendizado em desenvolvimento back-end.

## Escopo

### v0.1 — Somente leitura
- Conexão com Gmail via OAuth 2.0, com escopo mínimo de leitura de metadados.
- Análise sob demanda com período ou limite de mensagens.
- Agrupamento por lista (`List-ID`), com fallback e grau de confiança.
- Exibição de remetente, frequência, último envio, amostra de assuntos e método de cancelamento.
- Classificação 🔴 elegível / 🟡 decisão manual / 🟢 protegida.
- Links de cancelamento para ação manual.
- Desconexão e limpeza de dados locais.

### v0.2 — Cancelamento
- Seleção individual, em lote ou de todas as elegíveis.
- Confirmação com escopo exato.
- Cancelamento automático **somente** via RFC 8058 (one-click); demais casos como ação manual.
- Relatório de resultado por inscrição.

### Evolução futura (sem compromisso de data)
- Checagem semanal automática de novas inscrições.
- Classificação do tipo de conteúdo (promocional / transacional / informativo).
- Filtros, ordenação e histórico local.
- Avaliação de **integração com IA** para classificação ou resumo de inscrições, condicionada a requisitos de privacidade (preferência por processamento local).
- Outros provedores (ex.: Outlook) e múltiplas contas.

### Fora do escopo
- Visão geral da caixa por categoria (pessoal, faculdade etc.).
- Versão mobile ou servidor publicado.
- Excluir mensagens, criar filtros ou bloquear remetentes.
- Contornar CAPTCHA, login ou formulários de cancelamento.

## Fatos e hipóteses

| ID | Fato | Fonte |
|---|---|---|
| F1 | ~10 e-mails indesejados por semana | Relato do autor (estimativa) |
| F2 | E-mails importantes e de vagas se perdem | Relato do autor |
| F3 | A maior dor do cancelamento manual é a repetição | Relato do autor |
| F4 | Cancelamento manual pode exigir confirmação ou digitar o e-mail | Relato do autor |
| F5 | O Gmail possui gerenciamento nativo de inscrições, agrupado por remetente | Documentação Google |
| F6 | O recurso nativo exibe apenas o nome do remetente | Teste do autor |
| F7 | Já existem ferramentas locais e open source similares | Pesquisa pública |
| F8 | Etiquetar e-mails não elimina a origem | Relato do autor |

| ID | Hipótese | Validação |
|---|---|---|
| H1 | Classificar e-mails pessoais/faculdade exigiria escopo OAuth mais amplo | Fase 03 |
| H2 | Outras pessoas têm o mesmo problema | Não validada (limitação declarada) |
| H3 | A amostra de conteúdo é diferencial frente a concorrentes pagos | Opcional |
| H4 | `Subject` e `List-ID` estão disponíveis com o escopo `gmail.metadata` | Fase 03 |
| H5 | Parte relevante das inscrições suporta RFC 8058 | Fase 03 |

## Riscos

| ID | Risco |
|---|---|
| R1 | Escopo OAuth restrito pode exigir verificação do Google para distribuição pública |
| R2 | Remetentes podem ignorar solicitações de cancelamento |
| R3 | Recurso nativo e concorrentes maduros reduzem o valor como produto |
| R4 | Crescimento de escopo comprometer a conclusão do projeto |
