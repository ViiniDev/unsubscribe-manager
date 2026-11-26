# Critérios de aceitação da v0.1

Cada critério segue o formato Dado / Quando / Então e indica as regras de negócio que cobre (ver [Regras de negócio](business-rules.md)).

## RF01 Conectar a conta do Gmail

- **CA01.1** Dado que não há conta conectada, quando inicio a conexão, então o navegador abre a tela de consentimento do Google pedindo apenas o escopo `gmail.metadata`.
- **CA01.2** Dado que autorizei o acesso, quando o Google volta para o endereço local, então o token é salvo fora do repositório e a ferramenta indica que a conta está conectada.
- **CA01.3** Dado que neguei o acesso, quando volto para a ferramenta, então vejo que a conexão não foi feita e nenhum token é salvo.

## RF02 Iniciar a análise

- **CA02.1** Dado que a conta está conectada, quando inicio a análise sem alterar nada, então são lidas as mensagens dos últimos 90 dias, até o máximo de 500 (RN11).
- **CA02.2** Dado que escolhi 30 dias e 100 mensagens, quando inicio a análise, então nenhuma mensagem mais antiga que 30 dias é lida e a leitura para na 100ª mensagem.
- **CA02.3** Dado que informei zero ou um número negativo, quando tento iniciar a análise, então ela não começa e vejo o motivo.

## RF03 Identificar as inscrições

- **CA03.1** Dado uma mensagem com `List-Unsubscribe` ou `List-ID`, quando ela é analisada, então é considerada uma inscrição (RN01).
- **CA03.2** Dado uma mensagem sem nenhum dos dois cabeçalhos, quando ela é analisada, então não aparece no resultado (RN01).
- **CA03.3** Dado qualquer mensagem, quando ela é analisada, então só são pedidos os cabeçalhos `From`, `Subject`, `Date`, `List-ID`, `List-Unsubscribe` e `List-Unsubscribe-Post`, e o corpo não é lido (RN10).

## RF04 Agrupar por lista

- **CA04.1** Dado duas mensagens com o mesmo `List-ID` e remetentes diferentes, quando agrupo, então elas formam uma única inscrição com confiança alta (RN02, RN03).
- **CA04.2** Dado duas mensagens do mesmo remetente com `List-ID` diferentes, quando agrupo, então elas formam duas inscrições (RN03).
- **CA04.3** Dado mensagens sem `List-ID`, quando agrupo, então mensagens do mesmo endereço formam uma inscrição com confiança média, e endereços diferentes do mesmo domínio ficam separados (RN02).

## RF05 Mostrar as inscrições

- **CA05.1** Dado que a análise terminou, quando vejo o resultado, então cada inscrição mostra o nome da lista ou o remetente, o endereço, a quantidade de mensagens no período, a data do último envio e o método de cancelamento.
- **CA05.2** Dado um `List-Unsubscribe` com URL HTTPS e `List-Unsubscribe-Post` igual a `List-Unsubscribe=One-Click`, quando a inscrição é exibida, então o método é one-click (RN07).
- **CA05.3** Dado um `List-Unsubscribe` só com link HTTPS ou só com `mailto`, quando a inscrição é exibida, então o método é manual. Sem nenhum desses, o método é indisponível (RN07).

## RF14 Mostrar exemplos de assuntos

- **CA14.1** Dado uma inscrição com 5 mensagens, quando vejo seus detalhes, então aparecem os 3 assuntos mais recentes, do mais novo para o mais antigo (RN09).
- **CA14.2** Dado uma inscrição com 1 mensagem, quando vejo seus detalhes, então aparece apenas esse assunto.
- **CA14.3** Dado qualquer análise, quando ela termina, então nenhum assunto foi gravado em disco ou em logs (RN09).

## RF15 Classificar as inscrições

- **CA15.1** Dado uma inscrição com remetente na lista de domínios protegidos ou assunto com palavra-chave protegida, quando ela é classificada, então fica como protegida e não pode ser selecionada para cancelamento (RN04).
- **CA15.2** Dado uma inscrição que se encaixa ao mesmo tempo em protegida e em vagas, quando ela é classificada, então fica como protegida (RN04).
- **CA15.3** Dado uma inscrição de vagas, quando ela é classificada, então fica como decisão do usuário e não vem pré-selecionada (RN05).
- **CA15.4** Dado duas inscrições iguais exceto pela quantidade de mensagens, quando são classificadas, então recebem a mesma classificação (RN06).

## RF16 Mostrar o link para cancelamento manual

- **CA16.1** Dado uma inscrição com método manual e link HTTPS, quando ela é exibida, então o link aparece e só é aberto se eu clicar. A ferramenta não faz nenhuma requisição a ele (RN08).
- **CA16.2** Dado uma inscrição com `mailto`, quando ela é exibida, então aparece o endereço de e-mail para eu mesmo enviar o pedido.
- **CA16.3** Dado qualquer análise, quando consulto os logs, então nenhuma URL de cancelamento aparece completa (RN08).

## RF10 Desconectar a conta

- **CA10.1** Dado que a conta está conectada, quando desconecto, então o token é revogado no Google e o token e os dados da análise são apagados do computador (RN12).
- **CA10.2** Dado que a revogação no Google falhou, por exemplo sem internet, quando desconecto, então o token local é apagado mesmo assim e vejo um aviso para revogar o acesso manualmente na conta Google.