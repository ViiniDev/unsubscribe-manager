# Requisitos

Esta é a lista de requisitos funcionais com as prioridades de cada um. As regras de negócio estão em [Regras de negócio](business-rules.md) e os critérios de aceitação da v0.1 em [Critérios de aceitação](acceptance-criteria.md).

## Como priorizei

Usei a técnica MoSCoW:

- **Must:** obrigatório para a versão indicada.
- **Should:** importante, mas o produto funciona sem.
- **Could:** seria bom ter.
- **Won't:** fora do escopo por enquanto.

## Requisitos funcionais

A numeração segue a ordem em que os requisitos foram levantados. A tabela está organizada por versão.

### v0.1

| ID | Requisito | Prioridade |
|---|---|---|
| RF01 | Conectar a conta do Gmail via OAuth 2.0, só com leitura de metadados | Must |
| RF02 | Iniciar a análise escolhendo um período ou um limite de mensagens | Must |
| RF03 | Ler os cabeçalhos necessários e identificar as inscrições | Must |
| RF04 | Agrupar por lista (`List-ID`), com alternativa quando o cabeçalho não existir e indicação de confiança | Must |
| RF05 | Mostrar lista, remetente, frequência, último envio e como cancelar | Must |
| RF14 | Mostrar exemplos dos últimos assuntos de cada inscrição | Must |
| RF15 | Classificar cada inscrição em: pode cancelar, decisão do usuário ou protegida | Must |
| RF16 | Mostrar o link para cancelamento manual quando o remetente não suportar RFC 8058 | Must |
| RF10 | Desconectar a conta e apagar os dados locais | Must |

### v0.2

| ID | Requisito | Prioridade |
|---|---|---|
| RF06 | Selecionar uma inscrição, várias ou todas as que podem ser canceladas | Must |
| RF07 | Confirmar mostrando exatamente o que vai ser cancelado | Must |
| RF08 | Pedir o cancelamento somente via RFC 8058 | Must |
| RF09 | Registrar e mostrar o resultado de cada inscrição: solicitado, falhou ou ação manual | Must |

### Depois

| ID | Requisito | Prioridade |
|---|---|---|
| RF11 | Filtrar e ordenar as inscrições | Could |
| RF12 | Guardar um histórico local dos pedidos de cancelamento | Could |
| RF13 | Checar inscrições novas toda semana | Could |
| RF17 | Identificar o tipo de conteúdo: promoção, transacional ou informativo | Could |

Fica de fora por enquanto (Won't): visão da caixa por categoria, versão para celular, uso de IA, apagar mensagens ou criar filtros e outros provedores de e-mail.

## Requisitos não funcionais

Estes ainda são candidatos. Vou definir métricas para eles depois da prova de conceito com a Gmail API.

| ID | Requisito |
|---|---|
| RNF01 | Pedir a menor permissão possível no OAuth e nunca pedir senha |
| RNF02 | Guardar o mínimo de dados; nada de conteúdo real de e-mail em logs ou testes públicos |
| RNF03 | Proteger, revogar e apagar tokens e credenciais |
| RNF04 | Manter a interface respondendo enquanto a análise roda |
| RNF05 | Tratar falhas e os limites de uso da API |
| RNF06 | Código modular, testável e documentado |
| RNF07 | Execução local fácil de reproduzir |
| RNF08 | Interface acessível e confirmações claras antes de qualquer ação |
| RNF09 | Validar as requisições para links externos e evitar SSRF |
| RNF10 | Permitir outros provedores no futuro, sem complicar o projeto antes da hora |
