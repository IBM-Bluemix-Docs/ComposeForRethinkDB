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

# Connection Configuration
{: #connection-configuration}

{{site.data.keyword.composeForRethinkDB_full}} database connections are managed by a RethinkDB Proxy portal.

## Encryption in Transit

The {{site.data.keyword.composeForRethinkDB}} Proxy portal has TLS/SSL enabled and supports TLS version 1.2. The certificate for the service is a self-signed certificate. You may have to save a local copy of the certifcate for your serivce and provide it's location to your applications driver in order to make a secure connection.

## Connection Limits

Database connections have a connection limit of 2000 connections per portal. Exceeding the connection limit will make your service unresponsive. You can manage connections from your application through your driver's connection pooling feature.

## Proxy Timeouts

The Proxy portal manages the life cycle of connections between the server and client. We detail them here as a reference for driver writers and others who have an interest in the low-level activity of {{site.data.keyword.composeForRethinkDB}} database connections.

Setting | Value | Applies
----------|-----------|-----------
client | 5m | When the client is expect to acknowledge or send data.
connect | 4s | When a connection is being made between the proxy and the server.
server | 5m | When the server is expected to acknowledge or send data.
tunnel | 1 day | When a bidirectional connection is established between a client and a server, and the connection remains inactive in both directions.
client-fin | 1h | When the client is expected to acknowledge or send data while one direction is already shut down.
check | 5s | As a secondary timeout check when a connection is being made between the proxy and the server.
{: caption="Table 1. RethinkDB Proxy timeouts" caption-side="top"}
