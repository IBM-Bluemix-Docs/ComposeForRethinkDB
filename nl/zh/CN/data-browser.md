---

Copyright:
  years: 2017,2018
lastupdated: "2017-10-23"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:tip: .tip}

# 数据浏览器

{{site.data.keyword.composeForRethinkDB_full}} 服务随附有对 [RethinkDB 所提供的管理工具](https://www.rethinkdb.com/docs/administration-tools/)的访问权。

选择_数据浏览器_时会打开新选项卡。

可能会显示证书警告。生成证书警告是因为服务器的 SSL 证书是自签名证书。单击**添加例外**以继续。
{: .tip}

此时将显示登录对话框。您可以在服务的连接字符串中找到登录凭证。用户和密码在 `rethinkdb://` 之后和 `@` 之前的字符串部分中，格式为 `user:password`。

登录后，即可以使用管理工具来管理 Rethink 数据库集群和数据。 
