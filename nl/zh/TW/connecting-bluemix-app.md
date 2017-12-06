---

copyright:
  years: 2016,2017
lastupdated: "2017-06-17"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# 連接 {{site.data.keyword.cloud_notm}} 應用程式

若要將 {{site.data.keyword.cloud}} 應用程式連接至您的服務，請使用您在佈建服務時所建立的服務認證。範例應用程式會示範如何使用 Node.js，利用所提供的認證來連接至 {{site.data.keyword.composeForRethinkDB_full}} 服務，以及如何建立資料庫，然後從資料庫中讀取及寫入資料庫。

## 使用 'Hello World' 範例應用程式來連接

[compose-rethinkdb-helloworld-nodejs](https://github.com/IBM-Bluemix/compose-rethinkdb-helloworld-nodejs) 範例應用程式會示範如何使用 Node.js，利用所提供的認證來連接至 {{site.data.keyword.composeForRethinkDB}} 服務。應用程式會建立、讀取及寫入資料庫。

請下載範例應用程式，並遵循 Readme 檔中的指示。然後，在 {{site.data.keyword.cloud_notm}} 的應用程式詳細資料頁面中，按一下**檢視應用程式**來檢視*範例* 表格的內容。

## 可用的認證

欄位名稱|說明
----------|-----------
`uri`|要在連接至服務時使用的 URI。包括綱目 (rethinkdb:)、管理使用者名稱和密碼、伺服器的主機名稱，以及要連接至的埠號。
`uri_admin`|應該在瀏覽器中造訪以存取資料庫管理介面的 URI。需要來自 `uri` 欄位的管理使用者名稱和密碼才能進行存取。
`ca_certificate_base64`|用來確認應用程式將連接至適當伺服器的自簽憑證。這是 base64 編碼。您需要先解碼金鑰，才能使用金鑰（如範例應用程式中所示）。
`deployment_id`|Compose 內所建立之服務的內部 ID。
`db_type`|服務所提供的資料庫類型；在此情況下，為 `rethink`。
`name`|資料庫部署名稱。
{: caption="表 1. Compose for RethinkDB 認證" caption-side="top"}
