# 🤖 Assistente de Investimentos com RPA, n8n e IA Generativa

Projeto desenvolvido como parte de um desafio prático da [Digital Innovation One (DIO)](https://www.dio.me/), com o objetivo de automatizar a coleta e o processamento de dados de clientes e gerar mensagens personalizadas com o auxílio de Inteligência Artificial Generativa.

A solução utiliza Python para a automação da coleta de dados, n8n para orquestrar o fluxo de trabalho e Google Gemini para gerar mensagens personalizadas de acordo com o perfil de cada cliente e as opções de investimento elegíveis.

## 🎯 Objetivo do projeto

Construir um assistente automatizado capaz de:

- Extrair e processar dados de clientes por meio de Python.
- Enviar os dados ao n8n utilizando um Webhook HTTP.
- Consultar uma base de dados de investimentos em formato CSV.
- Filtrar opções de investimento conforme o perfil do cliente e o saldo disponível.
- Utilizar Inteligência Artificial Generativa para criar mensagens personalizadas.
- Organizar os resultados para consulta e validação.

## 🛠️ Tecnologias utilizadas

- **Python:** automação da coleta e envio de dados.
- **Google Colab:** execução do notebook Python.
- **n8n Cloud:** criação e execução do workflow de automação.
- **Webhooks HTTP:** comunicação entre Python e n8n.
- **JavaScript:** processamento e transformação dos dados no workflow.
- **Google Gemini:** geração de mensagens com Inteligência Artificial Generativa.
- **GitHub:** versionamento do código, documentação e armazenamento das evidências.

## ⚙️ Como funciona

O projeto é organizado em duas partes principais.

### 1. Automação e processamento dos dados

1. O script Python realiza a coleta dos dados dos clientes na página disponibilizada para o desafio.
2. Os dados coletados são enviados ao n8n por meio de um Webhook HTTP.
3. O workflow consulta a base de investimentos em CSV.
4. Os nós JavaScript processam os dados e filtram os investimentos elegíveis conforme os critérios definidos no projeto.
5. O fluxo prepara os dados de cada cliente para a geração das mensagens.

### 2. Geração de mensagens com IA

1. Os dados processados são encaminhados ao nó **Basic LLM Chain**.
2. O **Google Gemini Chat Model** utiliza a credencial configurada no n8n para gerar o texto.
3. A IA recebe informações como nome, perfil de investidor, saldo disponível e opções elegíveis.
4. O resultado é armazenado no campo `mensagemIA`, preservando os dados originais do cliente.
5. As mensagens geradas podem ser consultadas na saída da execução do workflow.

A IA é utilizada para redigir as mensagens. A seleção das opções elegíveis permanece sob responsabilidade da lógica de processamento do workflow.

## 🧩 Estrutura do repositório

```text
dio-lab-assistente-investimentos-rpa-n8n/
├── docs/
├── evidencias/
├── n8n/
│   └── workflow.json
├── rpa/
│   └── notebook de extração de clientes
└── README.md
```

A pasta `rpa/` contém o notebook Python utilizado na automação. A pasta `n8n/` contém o workflow exportado em JSON. A pasta `evidencias/` reúne capturas de tela dos testes e das execuções.

## 🚀 Como executar o projeto

### Pré-requisitos

- Conta no GitHub para acessar o código.
- Conta no Google Colab para executar o notebook Python.
- Acesso a uma instância do n8n Cloud.
- Credencial válida para utilizar o Google Gemini no n8n.

### Passo 1 — Acessar o projeto

Faça o fork deste repositório para sua conta do GitHub ou clone o projeto:

[Repositório do projeto](https://github.com/Kelencs/dio-lab-assistente-investimentos-rpa-n8n)

### Passo 2 — Executar o notebook Python

1. Abra o notebook localizado na pasta `rpa/`.
2. Importe o notebook para o Google Colab.
3. Confira as URLs utilizadas para acessar a página de clientes e enviar os dados ao Webhook.
4. Copie a URL correta do Webhook de teste ou de produção do seu workflow n8n.
5. Execute as células do notebook e verifique a resposta da requisição HTTP.

A URL do Webhook deve corresponder à configuração do workflow. No n8n, o modo de teste e o modo de produção podem utilizar URLs diferentes.

### Passo 3 — Importar o workflow no n8n

1. Abra o n8n Cloud.
2. Importe o arquivo `n8n/workflow.json`.
3. Confira as configurações dos nós e as conexões.
4. Configure o Webhook para receber os dados enviados pelo Python.
5. Salve o workflow.

### Passo 4 — Configurar o Google Gemini

1. No n8n, configure a credencial do Google Gemini Chat Model.
2. Utilize uma credencial disponível na sua conta ou configure uma chave de API válida.
3. Verifique se o nó Google Gemini Chat Model está conectado à entrada de modelo do Basic LLM Chain.
4. Confira o prompt utilizado para gerar as mensagens personalizadas.
5. Verifique os limites e os possíveis custos associados ao uso do modelo.

As credenciais devem ser configuradas diretamente no n8n. Não publique chaves de API, senhas ou outros segredos no GitHub.

### Passo 5 — Executar e validar

1. Execute o workflow utilizando o Webhook configurado.
2. Confira a execução dos nós de processamento.
3. Verifique se os clientes foram processados corretamente.
4. Abra a saída do nó responsável por formatar os resultados.
5. Confirme a presença dos dados originais e do campo `mensagemIA`.

## 🧪 Resultados dos testes

Durante os testes realizados no ambiente de desenvolvimento:

- O workflow processou 10 clientes.
- Os dados incluíram nome, perfil de investidor, saldo e opções elegíveis.
- O Google Gemini gerou mensagens personalizadas para os clientes processados.
- O campo `mensagemIA` foi incorporado aos dados originais de cada cliente.
- A integração foi executada sem necessidade de envio automático de e-mails.

As evidências visuais das execuções estão disponíveis na pasta [`evidencias/`](evidencias/).

## 🔐 Considerações importantes

Este projeto possui finalidade educacional e demonstra o uso de automação, integração de APIs e Inteligência Artificial Generativa.

Os dados e as rentabilidades utilizados na base de demonstração não devem ser considerados informações financeiras atuais ou garantidas.

As mensagens geradas não constituem recomendação de investimento. Antes de tomar decisões financeiras, é necessário avaliar os riscos, os custos, as condições dos produtos e os objetivos individuais.

O uso do Google Gemini pode estar sujeito a limites de utilização e cobranças, conforme a credencial e o plano configurados.

## 📚 Aprendizados

O desenvolvimento deste projeto permitiu praticar:

- Automação de processos com Python.
- Integração de aplicações por meio de Webhooks HTTP.
- Criação e orquestração de workflows no n8n.
- Manipulação de dados com JavaScript.
- Integração de modelos de linguagem em fluxos de automação.
- Versionamento de projetos e documentação técnica com GitHub.

## 👩‍💻 Autoria

Projeto desenvolvido como atividade prática de aprendizado, inspirado no desafio da Digital Innovation One sobre a criação de um assistente de investimentos com RPA e IA Generativa.

**Repositório:** [Kelencs/dio-lab-assistente-investimentos-rpa-n8n](https://github.com/Kelencs/dio-lab-assistente-investimentos-rpa-n8n)
