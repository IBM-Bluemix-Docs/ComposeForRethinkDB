---

copyright:
  years: 2016,2018
lastupdated: "2018-03-27"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# Sobre o {{site.data.keyword.composeForRethinkDB}}
{: #about-compose-for-rethinkdb}

O {{site.data.keyword.composeForRethinkDB_full}} dá a você um banco de dados distribuído, baseado em documento JSON, com um console integrado de administração e exploração. O RethinkDB usa a linguagem de consulta ReQL, que é construída com encadeamento de funções e está disponível nas bibliotecas do cliente para Java, JavaScript, Python e Ruby. Com a ReQL, é possível usar os recursos no lado do servidor RethinkDB, como junções e subconsultas distribuídas entre os nós do cluster. O RethinkDB também suporta índices secundários para melhor desempenho de consulta de leitura. O mais poderoso recurso do RethinkDB, changefeeds, permite que muitas consultas ReQL sejam convertidas em feeds em tempo real.
{:shortdesc}

**Nota:** todas as instâncias de serviço do Compose que foram
provisionadas antes de 14 de setembro de 2016 que ainda estiverem ativas poderão ser
usadas e acessadas diretamente em
[https://www.compose.com/](https://www.compose.com). Qualquer instância de serviço do Compose fornecida deste ponto em diante é acessada e usada diretamente dentro de sua conta do {{site.data.keyword.cloud}}.

## Criando uma instância de serviço do {{site.data.keyword.composeForRethinkDB}}

É possível criar um serviço do {{site.data.keyword.composeForRethinkDB}} por meio da página [{{site.data.keyword.composeForRethinkDB}}](https://console.{DomainName}/catalog/services/compose-for-rethinkdb/) no catálogo do {{site.data.keyword.cloud_notm}}.

Escolha um nome do serviço e uma região, organização e espaço no qual provisionar o serviço. É possível usar o campo **Selecionar uma versão do banco de dados** para escolher nas versões do banco de dados disponíveis.

Quando você provisiona sua instância do {{site.data.keyword.composeForRethinkDB}}, é possível escolher os planos *Padrão* ou *Corporativo*. Com o plano *Corporativo*, é possível provisionar sua instância do {{site.data.keyword.composeForRethinkDB}} em um cluster disponível do {{site.data.keyword.composeEnterprise}}. O {{site.data.keyword.composeEnterprise}} fornece a segurança e o isolamento requeridos pela conformidade corporativa e usa rede dedicada para assegurar o desempenho dos bancos de dados implementados. Consulte a  [ documentação do {{site.data.keyword.composeEnterprise}}  ](/docs/services/ComposeEnterprise/index.html)  para obter mais detalhes.

## Gerenciando {{site.data.keyword.composeForRethinkDB}}

É possível gerenciar seu serviço no painel de serviço. Aqui é possível localizar informações sobre o banco de dados do {{site.data.keyword.cloud_notm}} Compose e como conectar-se a ele. Também é possível:
- gerenciar seus backups
- alocar mais recursos para seu serviço
- mudar a senha do serviço
- use listas de desbloqueio para restringir o acesso a seus bancos de dados. 

Para obter mais informações, veja [Configurações](./dashboard-settings.html).

O {{site.data.keyword.composeForRethinkDB}} depende de funções do Cloud Foundry para gerenciar o acesso ao serviço. Somente usuários com a função de Desenvolvedor podem ver ou usar o painel de serviço. Para obter mais informações sobre as funções do Cloud Foundry, veja as páginas [Acesso ao Cloud Foundry](https://console.{DomainName}/docs/iam/cfaccess.html#cfaccess) e [Gerenciando ao acesso ao Cloud Foundry](https://console.{DomainName}/docs/iam/mngcf.html#mngcf).
{: .tip}

## Conectando-se ao {{site.data.keyword.composeForRethinkDB}}

É possível se conectar a seu serviço usando as credenciais que são criadas junto com o serviço ou com as sequências de conexões e linha de comandos que são fornecidas na guia *Visão geral* de seu painel de serviço.

## Conectando um aplicativo {{site.data.keyword.cloud_notm}} ao {{site.data.keyword.composeForRethinkDB}}

Para conectar um aplicativo {{site.data.keyword.cloud_notm}} a seu serviço, use as credenciais que são criadas com o serviço. É possível localizar informações sobre como conectar um aplicativo {{site.data.keyword.cloud_notm}} a um serviço {{site.data.keyword.composeForRethinkDB}} em [Conectando um aplicativo {{site.data.keyword.cloud_notm}}](./connecting-bluemix-app.html).

## Conectando-se ao {{site.data.keyword.composeForRethinkDB}} de fora do {{site.data.keyword.cloud_notm}}

Se você deseja se conectar ao {{site.data.keyword.composeForRethinkDB}} de fora do {{site.data.keyword.cloud_notm}}, é possível usar as sequências de conexões fornecidas ou a linha de comandos. É possível localizar informações sobre como conectar-se em [Conectando um aplicativo externo](./connecting-external.html).
