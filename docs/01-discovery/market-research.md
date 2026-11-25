# Pesquisa de concorrentes

Antes de começar, procurei ferramentas que já resolvem esse problema. É um levantamento feito a partir de fontes públicas, consultadas em 24/11/2026. Não conversei com usuários.

## Ferramentas que encontrei

| Ferramenta | O que faz | Preço | Observação |
|---|---|---|---|
| Gmail, "Gerenciar inscrições" | Lista as inscrições por frequência e cancela com um clique | Gratuito | Agrupa por remetente e está sendo liberado aos poucos por país e conta |
| Unroll.me | Cancelamento em massa | Gratuito | Teve um caso conhecido de privacidade: dados das caixas de entrada foram usados comercialmente pela empresa controladora, o que levou a um acordo com a FTC em 2019 |
| Clean Email | Limpeza geral da caixa, com uma função de cancelamento | Pago | Também manda para a lixeira os e-mails de listas que ignoram o cancelamento |
| Leave Me Alone | Cancelamento com foco em privacidade | Pago, com plano gratuito limitado | Precisa de acesso amplo à caixa de entrada |
| Inbox Zero | Assistente de e-mail que também cancela em massa | Assinatura, ou instalação própria | Open source, mas faz muito mais do que cancelar inscrições |
| Gmail Cleaner | Cancelamento em massa rodando localmente | Gratuito | Open source e com proposta parecida com a deste projeto |

## O que senti falta no Gmail

Testei o "Gerenciar inscrições" do Gmail na minha própria conta. O que mais fez falta foi saber que tipo de conteúdo cada inscrição envia. Os remetentes aparecem só pelo nome, como uma faculdade ou uma companhia aérea, sem dizer se mandam promoções, comunicados ou mensagens transacionais. Isso complica a decisão, principalmente quando o mesmo remetente manda promoções e também coisas importantes, como a confirmação de uma passagem.

## O que concluí

Ser local e open source não é exclusividade deste projeto, já que outras ferramentas fazem isso. Ainda assim, é algo que quero manter, porque garante privacidade e deixa qualquer pessoa conferir o código.

O que pretendo fazer diferente (é a hipótese H3, e não conferi todos os concorrentes a fundo):
- mostrar exemplos do que cada lista realmente envia;
- proteger por regra os e-mails sensíveis e deixar os alertas de vagas como decisão do usuário;
- ser honesto no resultado: um cancelamento "solicitado" não é o mesmo que "confirmado";
- agrupar por lista (`List-ID`), e não só por remetente.

## Fontes

- [Google: Gerenciar inscrições no Gmail](https://support.google.com/mail/answer/15621070)
- [Google Blog: Manage subscriptions (julho de 2025)](https://blog.google/products/gmail/new-manage-subscriptions-unsubscribe/)
- [FTC: acordo com a Unroll.me](https://www.ftc.gov/node/48064)
- [Clean Email: Unsubscriber](https://clean.email/unsubscriber)
- [Leave Me Alone](https://leavemealone.com/)
- [Inbox Zero no GitHub](https://github.com/elie222/inbox-zero)
- [Gmail Cleaner](https://gururagavendra.github.io/gmail-cleaner)
