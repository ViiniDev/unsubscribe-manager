# Especificação de Requisitos

> Fase 02 — Requisitos · Status: em andamento · Data: 2026-11-24
>
> Lista de RF e priorização MoSCoW definidas. Regras de negócio e critérios de aceitação (Given/When/Then) serão detalhados nas próximas tarefas.

## Priorização MoSCoW

- **Must:** obrigatório para a entrega indicada.
- **Should:** importante, mas o produto funciona sem.
- **Could:** desejável.
- **Won't:** fora do escopo atual.

## Requisitos funcionais

| ID | Requisito | Prioridade | Entrega |
|---|---|---|---|
| RF01 | Conectar conta Gmail via OAuth 2.0 (somente leitura de metadados) | Must | v0.1 |
| RF02 | Iniciar análise com período ou limite de mensagens configurável | Must | v0.1 |
| RF03 | Ler cabeçalhos necessários e identificar inscrições candidatas | Must | v0.1 |
| RF04 | Agrupar por identidade da lista (`List-ID`), com fallback e grau de confiança | Must | v0.1 |
| RF05 | Exibir lista, remetente, frequência, último envio e método de cancelamento | Must | v0.1 |
| RF14 | Exibir amostra dos últimos assuntos de cada inscrição | Must | v0.1 |
| RF15 | Classificar inscrições em 🔴 elegível / 🟡 decisão manual / 🟢 protegida | Must | v0.1 |
| RF16 | Exibir link de cancelamento para ação manual quando não houver RFC 8058 | Must | v0.1 |
| RF10 | Desconectar a conta e limpar dados locais | Must | v0.1 |
| RF06 | Selecionar individualmente, em lote ou todas as elegíveis | Must | v0.2 |
| RF07 | Exibir confirmação com escopo exato antes de cancelar | Must | v0.2 |
| RF08 | Solicitar cancelamento somente via RFC 8058 | Must | v0.2 |
| RF09 | Registrar e exibir resultado por inscrição (solicitado / falhou / ação manual) | Must | v0.2 |
| RF11 | Filtrar e ordenar inscrições | Could | Futuro |
| RF12 | Histórico local de solicitações | Could | Futuro |
| RF13 | Checagem semanal automática de novas inscrições | Could | Futuro |
| RF17 | Classificar tipo de conteúdo (promocional / transacional / informativo) | Could | Futuro |
| — | Visão por categoria, mobile, IA, exclusão/filtros, outros provedores | Won't | — |

## Requisitos não funcionais (candidatos)

> A detalhar com métricas somente após a prova de conceito (Fase 03).

| ID | Requisito |
|---|---|
| RNF01 | Menor privilégio OAuth e nenhuma coleta de senha |
| RNF02 | Minimização de dados; nenhum conteúdo real em logs ou testes públicos |
| RNF03 | Proteção, revogação e descarte de tokens e credenciais |
| RNF04 | Interface responsiva durante o processamento |
| RNF05 | Tratamento de falhas e de limites da API |
| RNF06 | Código modular, testável e documentado |
| RNF07 | Execução local reproduzível |
| RNF08 | Interface acessível e confirmação clara de ações |
| RNF09 | Segurança de requisições externas e prevenção de SSRF |
| RNF10 | Extensibilidade para outros provedores sem complexidade prematura |
