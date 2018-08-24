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

# 体系结构 
{: #architecture}

## 复制

{{site.data.keyword.composeForRethinkDB_full}} 服务使用一个具有三个数据节点的集群。选择部署了该服务的区域时，三个数据节点会分布在该区域的可用性专区中。RethinkDB 集群包含一个负责协调写操作的主成员。在发生节点故障时，其他成员可以成为主成员。如果一个数据成员变为不可访问，集群仍会继续正常运行。

### 设置数据复制

跨节点复制数据**不是**自动过程。数据将基于每个表的副本和分片计数分布在集群中。您必须将表配置为跨分片分布。有三种方法可以执行此操作。

1. 使用 RethinkDB Web 界面。内置 Web 界面的 URL 是在服务的_概述_页面上提供的_管理_连接字符串。您可以在此为所有表配置分片和复制。
2. 使用 `reconfigure` ReQL 命令。有关 `reconfigure` 的语法以及在不同语言中的用法的更多信息可以在 [ReQL 参考](https://www.rethinkdb.com/api/javascript/reconfigure/)中找到。
3. 通过将可选的 _replicas_ 参数用于 `tableCreate`，可以对应用程序进行编程，以在表创建时配置复制。有关 `tableCreate` 的语法以及在不同语言中的用法的更多信息可以在 [ReQL 参考](https://www.rethinkdb.com/api/javascript/table_create/)中找到。

## 磁盘加密

所有 {{site.data.keyword.composeForRethinkDB}} 服务都具有静态加密。数据位于启用了卷级别加密的服务器上。 

由于 {{site.data.keyword.composeForRethinkDB}} 是受管服务，因此 {{site.data.keyword.cloud}} Compose 操作员可以查看数据。除了磁盘加密外，还建议您在数据库中存储个人信息之前，对这些信息加密，或者使用扩展或功能启用对数据库本身的加密。虽然这些方法可能会影响可用性或性能，但确保个人信息受到加密保护是比较好的做法。

## 自动扩展

资源将根据 RethinkDB 数据库的磁盘存储总使用量自动进行扩展。内存使用量基于按 1:10 比率供应的存储量。这些资源会捆绑为单元。

自动扩展旨在响应数据库的中短期趋势。系统每小时会检查一次服务，如果服务的磁盘空间不足，那么会向部署分配更多单元。

自动扩展不会向下扩展部署，即减少磁盘/内存使用量。向数据库供应的资源将保留以满足您的未来需求，或者直到您手动向下扩展部署为止。
{: .tip}
