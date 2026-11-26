# Regras de negócio

Estas regras valem para a v0.1, que só lê os e-mails. Cada uma indica os requisitos que atende (ver [Requisitos](srs.md)).

## Identificação e agrupamento

| ID | Regra | Requisitos |
|---|---|---|
| RN01 | Uma mensagem só é tratada como inscrição se tiver o cabeçalho `List-Unsubscribe` ou `List-ID`. Mensagens sem nenhum dos dois, como e-mails pessoais ou da faculdade, não aparecem. | RF03 |
| RN02 | A inscrição é identificada pelo `List-ID`, com confiança alta. Sem `List-ID`, uso o endereço completo do remetente, com confiança média. Nunca agrupo só pelo domínio. | RF04 |
| RN03 | Um remetente pode ter várias listas e uma lista pode ter vários remetentes. Por exemplo, as promoções e as confirmações de uma mesma companhia aérea ficam separadas. | RF04 |

## Classificação

| ID | Regra | Requisitos |
|---|---|---|
| RN04 | Uma inscrição é protegida quando o remetente ou os assuntos indicam segurança, conta, banco, compras ou entregas, com base em palavras-chave e em uma lista de domínios configuráveis. Inscrição protegida nunca pode ser cancelada pela ferramenta. Na dúvida, ela é protegida. | RF15 |
| RN05 | Inscrições de vagas de emprego, identificadas por palavras-chave e domínios configuráveis, ficam para decisão do usuário e nunca vêm pré-selecionadas. | RF15 |
| RN06 | Frequência alta, sozinha, não torna uma inscrição elegível para cancelamento. | RF15 |

## Cancelamento manual

| ID | Regra | Requisitos |
|---|---|---|
| RN07 | O método é one-click quando o `List-Unsubscribe` tem uma URL HTTPS e o `List-Unsubscribe-Post` vale `List-Unsubscribe=One-Click`. Caso contrário, o método é manual (link HTTPS ou endereço `mailto`) ou indisponível. | RF05, RF16 |
| RN08 | Na v0.1 a ferramenta nunca acessa os links de cancelamento, apenas os mostra. URLs completas não são gravadas em logs. | RF16 |

## Dados e análise

| ID | Regra | Requisitos |
|---|---|---|
| RN09 | A amostra mostra até os 3 assuntos mais recentes de cada inscrição, apenas na tela, sem gravar em disco. | RF14 |
| RN10 | O corpo das mensagens nunca é lido nem armazenado. | RF03 |
| RN11 | A análise usa por padrão os últimos 90 dias e no máximo 500 mensagens, para respeitar a quota da API e o tempo de resposta. Os dois valores podem ser alterados pelo usuário. | RF02 |
| RN12 | Desconectar revoga o token no Google e apaga o token e os dados locais da análise. | RF10 |