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

# 連線配置
{: #connection-configuration}

{{site.data.keyword.composeForRethinkDB_full}} 資料庫連線由 RethinkDB Proxy 入口網站管理。

## 傳輸中加密

{{site.data.keyword.composeForRethinkDB}} Proxy 入口網站已啟用 TLS/SSL 且支援 TLS 1.2 版。服務的憑證是自簽憑證。您可能需要為服務儲存憑證的本端副本，並提供其位置給應用程式的驅動程式，以進行安全連線。

## 連線限制

資料庫連線具有每個入口網站各 2000 個連線的連線限制。超出連線限制時，您的服務就會無回應。您可以透過驅動程式的連線儲存區特性，管理來自應用程式的連線。

## Proxy 逾時

Proxy 入口網站會管理伺服器與用戶端之間連線的生命週期。此處會詳細說明它們，作為驅動程式撰寫者的參考資料，以及其他對 {{site.data.keyword.composeForRethinkDB}} 資料庫連線低階活動有興趣者的參考資料。

設定 |值|適用時機
----------|-----------|-----------
client | 5m |當用戶端預期要確認或傳送資料時。
connect | 4s |在 Proxy 和伺服器之間建立連線時。
server | 5m |當伺服器預期要確認或傳送資料時。
tunnel | 1 day |當在用戶端與伺服器之間建立雙向連線，且連線在雙向都保持非作用中時。
client-fin |1h|當用戶端預期要確認或傳送資料，而某個方向已關閉時。
check | 5s |作為次要的逾時檢查，在 Proxy 和伺服器之間建立連線時。
{: caption="表 1. RethinkDB Proxy 逾時" caption-side="top"}
