# Roadmap

Última atualização: 2026-11-24

## Onde o projeto está

A fase de descoberta foi concluída e os requisitos funcionais estão definidos. Ainda não há código executável: o próximo passo é a prova de conceito com a Gmail API.

## Versões

### v0.1 · Somente leitura (previsão: dezembro de 2026)
- Prova de conceito com OAuth 2.0 e leitura de cabeçalhos (valida H4 e H5).
- Agrupamento de inscrições por `List-ID`, amostra de assuntos e classificação em elegível, decisão manual ou protegida.
- Links para cancelamento manual.
- Testes e revisão de segredos antes da release.

### v0.2 · Cancelamento
- Seleção em lote com confirmação do escopo.
- Cancelamento automático apenas via RFC 8058 (one-click).
- Relatório de resultado por inscrição.

## Decisões tomadas

- O MVP foi dividido em duas entregas: primeiro somente leitura, depois cancelamento.
- O cancelamento automático só usa RFC 8058. Os demais casos viram ação manual, com o link.
- Stack: Java 17 com Spring Boot e Gmail API. A interface (web ou CLI) será decidida na fase de arquitetura.
- Se a leitura via OAuth não funcionar como esperado na prova de conceito, a v0.1 sai como CLI.

## Próximos passos

- Regras de negócio e critérios de aceitação dos requisitos obrigatórios.
- Projeto no Google Cloud e prova de conceito de leitura de cabeçalhos.
- Registro da decisão de arquitetura (ADR).

## Riscos

Ver [Visão e escopo](01-discovery/project-vision.md#riscos).
