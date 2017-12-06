---

copyright:
  years: 2017
lastupdated: "2017-10-16"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# 备份
{: #backups}

您可以从服务仪表板的*管理*页面创建和下载备份。可以使用安排的备份和手动备份。

## 查看现有备份

数据库的每日备份会自动安排。要查看现有备份，请浏览至服务仪表板的*管理*页面。 

![备份](./images/rethink-backups-show.png "服务仪表板中备份的列表")

单击相应的行以展开任何可用备份的选项。

![备份选项](./images/rethink-backups-options.png "备份选项") 

## 随需应变创建备份

除了已安排的备份，您还可以手动创建备份。要创建手动备份，请浏览至服务仪表板的*管理*页面，然后单击*立即备份*。

## 下载备份

要下载备份，请浏览至服务仪表板的*管理*页面，然后单击要下载的备份相应行中的*下载*。

## 备份内容

RethinkDB 备份使用正在运行的数据库集群上的 RethinkDB 命令行实用程序的 `dump` 命令，来备份整个部署。它会保存数据库、表内容以及元数据。`dump` 确实使用一些集群资源，但不会锁定客户机，并且可以在实时集群上运行。Compose 为 RethinkDB 部署提供备份，其格式可由 `rethinkdb restore` 直接使用。

## 将备份与本地数据库配合使用

由于 RethinkDB 备份可供您下载，所以您可以使部署的本地实例启动并运行。

1. 安装 [rethink](https://www.rethinkdb.com/docs/install/)
2. 在路径中安装 [python 驱动程序](https://www.rethinkdb.com/docs/install-drivers/python/)。
3. 下载压缩的备份文件。您不需要解压缩备份归档文件，RethinkDB 工具知道如何处理它。
4. 要旋转 RethinkDB，请在一个终端窗口中运行 `rethinkdb` 命令，而在另一个终端窗口中浏览到已下载备份的位置并运行 `rethinkdb restore backup.tar.gz`。

打开浏览器窗口并浏览至 `locahost:8080` 以查看 RethinkDB UI 和数据。

## 将本地备份引入您的服务

如果您在本地拥有要复原到 {{site.data.keyword.composeForRethinkDB}} 的备份文件，那么可以使用 `rethinkdb restore` 完成此操作。

1. 安装 [rethink](https://www.rethinkdb.com/docs/install/)
2. 在路径中安装 [python 驱动程序](https://www.rethinkdb.com/docs/install-drivers/python/)。
3. 从服务的*概述*页面下载证书，并在本地将其保存为 compose.cert。
4. 使用以下命令从备份复原：

  ```
  rethinkdb restore -c <host>:<port> --tls-cert compose.cert -p backup.tar.gz
  ```

可以在服务的*概述*页面上找到连接字符串中的主机和端口值。命令中的 `-p` 将提示输入_认证凭证_。

**注：**如果要复原到现有部署，那么可能必须使用 `--force` 来覆盖现有表。
