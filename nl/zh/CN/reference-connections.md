---
copyright:
  years: 2016,2018
lastupdated: "2018-06-14"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:tip: .tip}

# 连接配置
{: #connection-configuration}

{{site.data.keyword.composeForRethinkDB_full}} 数据库连接通过 RethinkDB 代理门户网站进行管理。

## 传输中加密

{{site.data.keyword.composeForRethinkDB}} 代理门户网站已启用 TLS/SSL，并且支持 TLS V1.2。该服务的证书是自签名证书。您可能必须保存用于服务的证书的本地副本，并为应用程序驱动程序提供该副本的位置，以便建立安全连接。

## 连接限制

数据库连接的连接限制为每个门户网站 2000 个连接。超过连接限制将使服务无响应。可以通过驱动程序的连接池功能来管理应用程序的连接。

## 代理超时

代理门户网站可管理服务器与客户机之间连接的生命周期。我们在此详细描述的信息供驱动程序作者以及对 {{site.data.keyword.composeForRethinkDB}} 数据库连接低级别活动有兴趣的其他人员作为参考。

设置|值|适用情况
----------|-----------|-----------
client|5 分钟|客户机应该确认或发送数据的时间。
connect|4 秒|在代理与服务器之间建立连接的时间。
server|5 分钟|服务器应该确认或发送数据的时间。
tunnel|1 天|客户机与服务器之间建立双向连接，并且连接在两个方向均保持不活动状态的时间。
client-fin|1 小时|服务器应该确认或发送数据，但一个方向的连接已关闭的时间。
check|5 秒|作为辅助超时，是指检查代理与服务器之间是否建立连接的时间。
{: caption="表 1. RethinkDB 代理超时" caption-side="top"}
