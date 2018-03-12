---

copyright:
  years: 2016,2018
lastupdated: "2017-06-17"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# Conectando um aplicativo {{site.data.keyword.cloud_notm}}

Para conectar um aplicativo {{site.data.keyword.cloud}} a seu serviço, use as credenciais de serviço que são criadas quando o serviço é provisionado. O aplicativo de amostra demostra como usar o Node.js para se conectar a um serviço {{site.data.keyword.composeForRethinkDB_full}} usando as credenciais fornecidas e como criar um banco de dados e ler e gravar no banco de dados.

## Conectando usando o aplicativo de amostra 'Hello World'

O aplicativo de amostra [compose-rethinkdb-helloworld-nodejs](https://github.com/IBM-Bluemix/compose-rethinkdb-helloworld-nodejs) demonstra como usar o Node.js para se conectar a um serviço {{site.data.keyword.composeForRethinkDB}} usando as credenciais fornecidas. O aplicativo cria, lê e grava em um banco de dados

Faça download do aplicativo de amostra e siga as instruções no arquivo leia-me. Em seguida, em sua página de detalhes do aplicativo no {{site.data.keyword.cloud_notm}}, clique em **Visualizar app** para visualizar os conteúdos da tabela *exemplos*.

## Credenciais disponíveis

Campo de nome|Descrição
----------|-----------
`uri`|O URI a ser usado na conexão com o serviço. Inclui o esquema
(rethinkdb:), o nome do usuário administrativo e a senha, o nome do host do servidor e o
número da porta à qual se conectar.
`uri_admin`|Um URI que deve ser visitado em um navegador para acessar a interface de administração do banco de dados. O acesso requer o nome do usuário administrativo e a senha no campo `uri`.
`ca_certificate_base64`|Um certificado autoassinado que é usado para confirmar se um aplicativo está se conectando ao servidor apropriado. Isso é codificado em base64. É preciso decodificar a chave antes de usá-la, conforme mostrado no aplicativo de amostra.
`deployment_id`|Um identificador interno para o serviço conforme criado no Compose.
`db_type`|O tipo de banco de dados que é oferecido pelo serviço; nesse caso, `rethink`.
`name`|O nome da implementação do banco de dados.
{: caption="Tabela 1. Credenciais do Compose for RethinkDB" caption-side="top"}
