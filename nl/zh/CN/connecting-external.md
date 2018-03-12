---

copyright:
  years: 2017,2018
lastupdated: "2017-06-17"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# 连接外部应用程序
{: #connecting-external-app}

根据您使用的驱动程序，有多种方法可连接到 RethinkDB。{{site.data.keyword.composeForRethinkDB_full}} 使用 URI 格式连接字符串：

```
rethinkdb://[username]:[password]@[host]:[port]/
```

您将在 {{site.data.keyword.composeForPostgreSQL}} 服务的*概述*页面上找到连接字符串。

## 使用 SSL 进行连接 - 应用程序

目前，据我们所知，所有四个官方支持的 RethinkDB 驱动程序（JavaScript、Python、Ruby 和 Java）以及 Go 驱动程序 (gorethink) 支持通过 SSL 进行连接。如果您正在使用其他驱动程序且 SSL 连接有问题，那么您可能希望与驱动程序维护人员联系，让他们了解您希望对 RethinkDB 提供 SSL 支持的程度。

为了确保连接安全，并防止发生中间人攻击，您需要抓取公用密钥以进行部署。一旦您具有公用密钥和连接信息（主机、端口、认证密钥），请查看特定驱动程序文档，以获取正确的连接设置，或者查看此 Compose 文章，以获取 [Python、Ruby、Node/JavaScript 和 Go 连接示例](https://www.compose.io/articles/rethinkdb-and-ssl-think-secure/)；如果您正在使用 Rethink 2.3 并希望以其他用户身份进行连接，请参阅此 Compose 文章，其位于*[使用 RethinkDB 2.3 的用户认证](https://compose.io/articles/using-rethinkdb-2-3s-user-authentication/)*。

要获取深度应用程序和驱动程序支持，请查看您特定语言的相应文档和社区，以及应用程序正在使用的驱动程序。

- http://rethinkdb.com/api/javascript/connect/
- http://rethinkdb.com/api/python/connect/
- http://rethinkdb.com/api/ruby/connect/
- http://rethinkdb.com/api/java/connect/
- https://github.com/dancannon/gorethink#gorethink---rethinkdb-driver-for-go
