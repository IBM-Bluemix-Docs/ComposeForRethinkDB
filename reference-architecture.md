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

# Architecture 
{: #architecture}

## Replication

An {{site.data.keyword.composeForRethinkDB_full}} service uses a cluster with three data nodes. When you select a region where the service is deployed, the three nodes are spread over the region's availability zones. Clusters consist of a master member, which coordinates writes, and more members that can become the master. If one data member becomes unreachable, your cluster continues to operate normally.

### Setting up Replication of your data

Replication of your data across nodes is **not** an automatic process. The data is spread across the cluster based on the replica and shard count of each table. You need to configure your tables to spread across shards, which you can do in three ways.

1. Use the RethinkDB web Interface. The URL for the built-in web interface is the _Admin_ connection string that is provided on your service's _Overview_ page. You can configure sharding and replication for all of your tables there.
2. Use the `reconfigure` ReQL command. More on the syntax of `reconfigure` with usage in different languages can be found in the [ReQL reference](https://www.rethinkdb.com/api/javascript/reconfigure/).
3. You can program your application to configure replication at table creation by using the optional _replicas_ parameter to `tableCreate`. More on the syntax of `tableCreate` with usage in different languages can be found in the [ReQL reference](https://www.rethinkdb.com/api/javascript/table_create/).

## Disk Encryption

All {{site.data.keyword.composeForRethinkDB}} services have encryption at rest. Your data resides on servers that have volume-level encryption enabled. 

Because {{site.data.keyword.composeForRethinkDB}} is a managed service, {{site.data.keyword.cloud}} Compose operators can see data. In addition to the disk encryption, we recommend that you encrypt personal information before it is stored in the database, or use extensions or features to enable encryption on the database itself. While these methods might impact usability or performance, it is good practice to ensure that personal information is protected with encryption.

## Auto-scaling

Resources are scaled automatically based on the total disk storage use of the RethinkDB databases. Memory usage is based on a ratio of provisioned storage at a ratio of 1:10. These resources are bundled as units.

Auto-scaling is designed to respond to the short-to-medium term trends of your database. Every hour, your service is checked, and if it is running short on disk space, then more units are allocated to the deployment.

Auto-scaling does not scale down deployments when disk/memory usage shrinks. The resources provisioned to your databases will remain for your future needs, or until you scale down your deployment manually.
{: tip}
