---
copyright:
  years: 2016,2018
lastupdated: "2018-06-14"

subcollection: compose-for-rethinkdb

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:tip: .tip}

# Connection Architecture
{: #connection-architecture}

{{site.data.keyword.composeForRethinkDB_full}} database connections are managed by a RethinkDB Proxy portal.

## Encryption in Transit

The {{site.data.keyword.composeForRethinkDB}} Proxy portal has TLS/SSL enabled and supports TLS version 1.2. The certificate for the service is a self-signed certificate. You might need to save a local copy of the certificate for your service and provide its location to your applications driver to make a secure connection.

## Connection Limits

Database connections have a limit of 2000 connections per portal. Exceeding this limit will make your service unresponsive. You can manage connections from your application through your driver's connection pooling feature.

## Proxy Timeouts

The Proxy portal manages the lifecycle of connections between the server and client. We detail them here as a reference for driver writers and others who have an interest in the low-level activity of {{site.data.keyword.composeForRethinkDB}} database connections.

Setting | Value | Applies
----------|-----------|-----------
`client` | 5 m | When the client is expected to acknowledge or send data.
`connect` | 4 s | When a connection is being made between the proxy and the server.
`server` | 5 m | When the server is expected to acknowledge or send data.
`tunnel` | 1 day | When a bidirectional connection is established between a client and a server, and the connection remains inactive in both directions.
`client-fin` | 1 h | When the client is expected to acknowledge or send data while one direction is already shut down.
`check` | 5 s | As a secondary timeout check when a connection is being made between the proxy and the server.
{: caption="Table 1. RethinkDB Proxy timeouts" caption-side="top"}
