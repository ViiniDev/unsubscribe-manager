# Unsubscribe Manager

Projeto em desenvolvimento. Por enquanto só existem a documentação e os requisitos; o código começa na próxima etapa.

Um gerenciador de inscrições do Gmail que roda na sua máquina. A ideia é mostrar o que cada lista de e-mail realmente envia e cancelar em lote só o que for seguro, sem tocar em e-mails importantes e deixando as decisões mais delicadas com você.

## Por que estou fazendo isso

Depois de me cadastrar em lojas, redes sociais e sites de vagas, minha caixa de entrada começou a receber promoções e notificações toda semana. No meio disso, e-mails que importavam, inclusive de vagas, passavam despercebidos.

Cancelar uma inscrição de cada vez é cansativo, e eu sempre desistia no meio. O Gmail tem um gerenciador de inscrições, mas ele mostra só o nome do remetente. Isso não basta para decidir: uma companhia aérea, por exemplo, manda promoções e também a confirmação da passagem.

Mais detalhes na [definição do problema](docs/01-discovery/problem-statement.md).

## O que está planejado

### v0.1: somente leitura
- [ ] Conectar ao Gmail com OAuth 2.0, pedindo o mínimo de permissão
- [ ] Encontrar as inscrições pelos cabeçalhos `List-ID` e `List-Unsubscribe`
- [ ] Agrupar por lista, e não só por remetente
- [ ] Mostrar os últimos assuntos de cada inscrição
- [ ] Nunca sugerir cancelar e-mails de segurança, bancos ou compras
- [ ] Mostrar o link para cancelar manualmente

### v0.2: cancelamento
- [ ] Selecionar várias inscrições e confirmar antes de cancelar
- [ ] Cancelar com segurança pelo padrão RFC 8058 (one-click)
- [ ] Mostrar o resultado de cada cancelamento

## Documentação

| Documento | O que tem |
|---|---|
| [Roadmap](docs/ROADMAP.md) | Versões, decisões e próximos passos |
| [Definição do problema](docs/01-discovery/problem-statement.md) | O problema, tipos de e-mail, para quem é e jornada |
| [Pesquisa de concorrentes](docs/01-discovery/market-research.md) | Ferramentas parecidas e o que muda aqui |
| [Visão e escopo](docs/01-discovery/project-vision.md) | O que entra, o que fica de fora, hipóteses e riscos |
| [Requisitos](docs/02-requirements/srs.md) | Requisitos e prioridades |

## Tecnologias

- Java 17 e Spring Boot
- Gmail API com OAuth 2.0, só com leitura de metadados
- Interface web ou de linha de comando, ainda a decidir

## Privacidade

- Tudo roda localmente. Os seus e-mails não passam por nenhum servidor do projeto.
- O app não pede permissão para enviar nem para apagar mensagens.
- Nenhuma credencial ou e-mail real vai para o repositório.

## Licença

[MIT](LICENSE)