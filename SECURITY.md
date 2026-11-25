# Política de segurança

O Unsubscribe Manager acessa contas do Gmail, então levo a segurança do projeto a sério.

## Como reportar uma vulnerabilidade

Se encontrar uma falha de segurança, não abra uma issue pública. Use a opção "Report a vulnerability", na aba Security deste repositório, ou mande um e-mail para viniciusarruda189@gmail.com com:

- uma descrição do problema;
- os passos para reproduzir;
- o impacto que você imagina que ele pode ter.

Respondo em até 7 dias e aviso quando a correção estiver pronta.

## Versões com suporte

O projeto ainda está em desenvolvimento e não tem versão estável. As correções de segurança entram sempre no branch `develop`.

## Cuidados que o projeto segue

- Tudo roda localmente. Os e-mails não passam por nenhum servidor do projeto.
- O app pede só permissão de leitura de metadados no OAuth, sem permissão para enviar ou apagar mensagens.
- Nenhuma credencial, token ou e-mail real é guardado no repositório. Arquivos como `client_secret*.json`, `credentials*.json` e `.env` estão no `.gitignore`.
- O cancelamento automático vai usar só o padrão RFC 8058, e os links externos serão validados antes de qualquer requisição.
