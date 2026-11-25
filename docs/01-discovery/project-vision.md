# Visão e escopo

## A ideia em uma frase

Um gerenciador de inscrições do Gmail que roda localmente, mostra o que cada lista de e-mail realmente envia e cancela em lote só o que é seguro, sem tocar em e-mails importantes.

## Como deve funcionar

O Unsubscribe Manager se conecta à conta do Gmail, encontra as listas de e-mail que chegam na caixa de entrada e mostra o que cada uma costuma enviar. A partir disso, dá para cancelar várias inscrições de uma vez com segurança. E-mails críticos ficam protegidos, e o resultado de cada cancelamento aparece no final, inclusive quando ele não deu certo.

O objetivo é resolver um problema que eu tenho no dia a dia e, no caminho, aprender mais sobre desenvolvimento back-end.

## O que entra em cada versão

### v0.1: somente leitura
- Conexão com o Gmail via OAuth 2.0, só com permissão de leitura de metadados.
- Análise sob demanda, escolhendo um período ou um limite de mensagens.
- Agrupamento por lista (`List-ID`). Quando o cabeçalho não existir, o agrupamento é feito de outra forma e a ferramenta indica o quanto confia nele.
- Para cada inscrição: remetente, frequência, último envio, exemplos de assuntos e como cancelar.
- Classificação em três grupos: pode cancelar, decisão do usuário e protegida.
- Link para cancelar manualmente.
- Opção de desconectar a conta e apagar os dados locais.

### v0.2: cancelamento
- Selecionar uma inscrição, várias ou todas as que podem ser canceladas.
- Confirmar vendo exatamente o que vai ser cancelado.
- Cancelamento automático apenas quando o remetente suporta o padrão RFC 8058 (one-click). Nos outros casos, a ferramenta mostra o link para cancelar à mão.
- Resultado de cada cancelamento.

### Depois, sem data definida
- Checagem semanal de inscrições novas.
- Identificar o tipo de conteúdo de cada lista: promoção, mensagem transacional ou informativo.
- Filtros, ordenação e histórico local.
- Avaliar o uso de IA para classificar ou resumir as inscrições, de preferência processando tudo localmente por causa da privacidade.
- Outros provedores, como o Outlook, e mais de uma conta.

### O que não faz parte do projeto
- Organizar a caixa de entrada por categoria (pessoal, faculdade etc.).
- Versão para celular ou servidor publicado na internet.
- Apagar mensagens, criar filtros ou bloquear remetentes.
- Passar por CAPTCHA, login ou formulários nas páginas de cancelamento.

## O que ainda preciso confirmar

O que já sei veio da minha própria caixa de entrada e da pesquisa de concorrentes (detalhes na [definição do problema](problem-statement.md) e na [pesquisa de concorrentes](market-research.md)). Algumas coisas ainda são hipóteses:

- **H1.** Classificar e-mails pessoais ou da faculdade exigiria uma permissão de OAuth maior do que a planejada. Vou verificar na prova de conceito.
- **H2.** Outras pessoas têm o mesmo problema. Ainda não validei, e por enquanto o projeto parte da minha experiência.
- **H3.** Mostrar exemplos do conteúdo de cada lista é um diferencial em relação às ferramentas pagas.
- **H4.** Os cabeçalhos `Subject` e `List-ID` estão disponíveis com a permissão `gmail.metadata`. Vou verificar na prova de conceito.
- **H5.** Uma parte relevante das inscrições suporta o RFC 8058. Também vou verificar na prova de conceito.

## Riscos

- **Verificação do Google:** a permissão de leitura do Gmail é considerada restrita. Para distribuir o app publicamente seria preciso passar pela verificação do Google. Como a ferramenta roda localmente, cada pessoa pode criar o próprio projeto no Google Cloud e usar o app em modo de teste.
- **Remetentes que ignoram o cancelamento:** pedir o cancelamento não garante que ele aconteça. Por isso a ferramenta mostra o pedido como "solicitado", e não como "concluído".
- **Concorrência:** o próprio Gmail e outras ferramentas já resolvem parte do problema, o que diminui o valor do projeto como produto.
- **Escopo crescendo demais:** o maior risco para terminar o projeto é ir adicionando funcionalidades. Por isso as versões estão separadas.
