# Assistente de Investimentos com RPA e n8n

## Sobre o projeto

Projeto desenvolvido como parte de um desafio prático da DIO para automatizar o processamento de dados de clientes e gerar mensagens personalizadas conforme o perfil de investidor e o saldo disponível.

## Tecnologias utilizadas

- Python
- Google Colab
- n8n
- Webhook HTTP
- JavaScript
- GitHub

## Como funciona

1. O Python extrai os dados dos clientes.
2. Os dados são enviados ao n8n por meio de um Webhook HTTP.
3. O n8n consulta uma base de investimentos em CSV.
4. Os investimentos são filtrados de acordo com o perfil e o saldo de cada cliente.
5. O fluxo gera mensagens personalizadas com as opções encontradas.

## Estrutura do projeto

- `rpa/`: notebook Python de extração dos clientes.
- `n8n/workflow.json`: workflow exportado do n8n.
- `evidencias/`: capturas de tela que demonstram a execução.
- `README.md`: documentação do projeto.

## Como executar

1. Abra o notebook Python disponível na pasta `rpa/` usando o Google Colab.
2. Execute as células necessárias para extrair os dados dos clientes.
3. Configure e publique o workflow no n8n.
4. Confira se a URL do Webhook no notebook corresponde à URL de produção do workflow publicado.
5. Execute o notebook e verifique a execução no n8n.
6. Confira as mensagens geradas na saída do último nó.

**Observação:** não publique tokens, senhas ou credenciais no repositório.

## Evidências

As capturas de tela da execução estão disponíveis na pasta [`evidencias`](evidencias/).

## Resultado

O fluxo foi executado com sucesso no n8n, processando 10 clientes e gerando mensagens personalizadas com opções de investimento conforme os critérios definidos no projeto.

## Observação sobre os dados

Este projeto tem finalidade educacional. Os dados de rentabilidade utilizados são demonstrativos e não constituem recomendação de investimento. As taxas apresentadas não representam necessariamente condições atuais de mercado.

## Autoria

Projeto desenvolvido como atividade prática de aprendizado em automação com Python, RPA e n8n.

