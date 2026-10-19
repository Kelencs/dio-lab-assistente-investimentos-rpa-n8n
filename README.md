# Assistente de Investimentos com RPA e n8n

## Sobre o projeto

Este projeto foi desenvolvido como parte de um desafio prático da DIO, com o objetivo de automatizar o processamento de dados de clientes e gerar mensagens personalizadas de acordo com o perfil de investidor e o saldo disponível.

## Tecnologias utilizadas

- Python
- Google Colab
- n8n
- Webhook HTTP
- JavaScript
- GitHub

## Como funciona

1. O Python realiza a extração dos dados dos clientes.
2. Os dados são enviados ao n8n por meio de um Webhook.
3. O n8n consulta uma base de investimentos em CSV.
4. Os investimentos são filtrados conforme o perfil e o saldo de cada cliente.
5. O fluxo gera mensagens personalizadas com as opções encontradas.

## Estrutura do projeto

- `src/`: código Python e notebook de extração.
- `n8n/workflow.json`: fluxo de automação exportado.
- `evidencias/`: capturas de tela da execução.
- `README.md`: documentação do projeto.

## Evidências

As capturas de tela da execução estão disponíveis na pasta [`evidencias`](evidencias/).

## Resultado

O fluxo foi executado com sucesso no n8n, processando 10 clientes e gerando mensagens personalizadas com opções de investimento conforme os critérios definidos no projeto.

## Observação

Este projeto tem finalidade educacional. Os dados de rentabilidade utilizados são demonstrativos e não constituem recomendação de investimento.

## Autoria

Projeto desenvolvido como atividade prática de aprendizado em automação com Python, n8n e RPA.
