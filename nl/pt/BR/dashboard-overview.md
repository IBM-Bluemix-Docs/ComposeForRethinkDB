---

Copyright:
  years: 2017,2018
lastupdated: "2018-05-07"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# Visão geral do serviço

A página _Visão geral_ mostra informações sobre seu banco de dados do Compose do {{site.data.keyword.cloud}}. A visão geral inclui informações essenciais de identificação e o uso do recurso atual. Você também localizará uma seção para sequências de conexões que podem ser usadas com ferramentas ou fazer uso de ferramentas para se conectar a seu banco de dados.

## Detalhes da implementação

O painel _Detalhes da implementação_ mostra detalhes de seu serviço.

![Deployment Details](./images/rethink-deployment-details.png "A view of the Deployment Details panel")

### Tipo

O tipo de banco de dados que é oferecido pelo serviço e a versão do banco de dados que seu serviço usa. Se uma versão de banco de dados mais recente estiver disponível, uma notificação será exibida, junto a um link para a seção [Fazer upgrade da versão](/docs/services/ComposeForRethinkDB/dashboard-settings.html#upgrade-version) de seu painel de serviço.

### ID

Um identificador interno para o serviço.

### Uso

O tamanho de seu banco de dados e a quantia de armazenamento fornecido por seu plano de serviço.

## Tarefas atuais

Fazer mudanças administrativas em seu serviço (como ajuste de escala ou execução de um backup manual) inicia uma tarefa. Enquanto uma tarefa estiver em execução, o painel _Tarefas atuais_ aparecerá na página _Visão geral_, mostrando o nome da tarefa e uma barra de progresso. Quando a tarefa for concluída, o painel _Tarefas atuais_ não aparecerá mais na página _Visão geral_.

## Sequências de conexões

Você localizará cada Sequência de conexões para seu serviço em uma guia diferente no painel _Sequências de conexões_.

### HTTPS

Uma sequência de conexões formatadas por URI que pode ser usada por algumas bibliotecas do cliente e contém todas as informações necessárias para outras bibliotecas se conectarem. É possível descobrir como usar a Sequência de conexões para conectar-se em [Conectando um aplicativo externo](./connecting-external.html).

### Administrador

O link na guia **Administrador** abrirá o _Console de administração do RethinkDB_. As informações de login estão na sequência de conexões **HTTPS** após o 'rethinkdb://' e antes do '@'.

### Certificado SSL

Seu serviço Compose {{site.data.keyword.cloud_notm}} fornece um certificado SSL que é possível usar para conectar-se a seu banco de dados.


## API de administração de instância

É possível gerenciar o serviço {{site.data.keyword.composeForRethinkDB}} por meio da API do {{site.data.keyword.cloud_notm}} Compose.

### Terminal de base

O terminal base é composto pela região na qual o serviço reside e pelo ID da instância de serviço. Ela estará no início de cada terminal.

### ID de implementação

O ID de implementação é necessário para a maioria das chamadas e identifica a instância de implementação específica.

### Referência

Para obter mais documentação e referência para usar a API Compose do {{site.data.keyword.cloud_notm}}, ao longo de todos os serviços Compose do {{site.data.keyword.cloud_notm}}, leia [A API Compose do {{site.data.keyword.cloud_notm}}](https://www.compose.com/articles/the-ibm-cloud-compose-api/).
