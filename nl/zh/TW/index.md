---

copyright:
  years: 2016,2018
lastupdated: "2018-03-27"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# 關於 {{site.data.keyword.composeForRethinkDB}}
{: #about-compose-for-rethinkdb}

{{site.data.keyword.composeForRethinkDB_full}} 使用整合式管理及探索主控台來提供 JSON 文件型分散式資料庫。RethinkDB 所使用的 ReQL 查詢語言是根據功能鏈結所建置，且位於 Java、JavaScript、Python 及 Ruby 的用戶端程式庫中。使用 ReQL，可以跨叢集節點使用 RethinkDB 伺服器端特性（例如分散式結合及子查詢）。RethinkDB 也支援次要索引，以獲得較佳的讀取查詢效能。RethinkDB 最強大的特性 changefeeds，容許將許多 ReQL 查詢轉換為即時資訊來源。
{:shortdesc}

**附註：**在 2016 年 9 月 14 日之前佈建且仍然作用中的任何 Compose 服務實例，仍然可以使用，而且可以在 [https://www.compose.com/](https://www.compose.com) 直接存取。從這個時間點以後佈建的任何 Compose 服務實例，可以在 {{site.data.keyword.cloud}} 帳戶內直接存取及使用。

## 建立 {{site.data.keyword.composeForRethinkDB}} 服務實例

您可以從 {{site.data.keyword.cloud_notm}} 型錄中的 [{{site.data.keyword.composeForRethinkDB}} 頁面](https://console.{DomainName}/catalog/services/compose-for-rethinkdb/)建立 {{site.data.keyword.composeForRethinkDB}} 服務。

選擇服務名稱，以及要在其中佈建服務的地區、組織和空間。您可以使用**選取資料庫版本**欄位，從可用的資料庫版本中進行選擇。

當您佈建 {{site.data.keyword.composeForRethinkDB}} 實例時，可以選擇*標準* 或*企業* 方案。使用*企業* 方案，您可以將 {{site.data.keyword.composeForRethinkDB}} 實例佈建到可用的 {{site.data.keyword.composeEnterprise}} 叢集。{{site.data.keyword.composeEnterprise}} 提供企業法規遵循所需的安全和隔離，並使用專用網路來確保已部署之資料庫的效能。如需詳細資料，請參閱 [{{site.data.keyword.composeEnterprise}} 文件](/docs/services/ComposeEnterprise/index.html)。

## 管理 {{site.data.keyword.composeForRethinkDB}}

您可以從服務儀表板來管理服務。在這裡，您可以找到 {{site.data.keyword.cloud_notm}} Compose 資料庫的相關資訊，以及連接方式。您也可以：
- 管理備份。
- 為您的服務配置更多資源。
- 變更服務密碼。
- 使用白名單來限制對資料庫的存取權。 

如需相關資訊，請參閱[設定](./dashboard-settings.html)。

{{site.data.keyword.composeForRethinkDB}} 根據 Cloud Foundry 角色來管理對服務的存取權。只有具有「開發人員」角色的使用者才能看到或使用服務儀表板。如需 Cloud Foundry 角色的相關資訊，請參閱 [Cloud Foundry 存取](https://console.{DomainName}/docs/iam/cfaccess.html#cfaccess)及[管理 Cloud Foundry 存取](https://console.{DomainName}/docs/iam/mngcf.html#mngcf)頁面。
{: .tip}

## 連接至 {{site.data.keyword.composeForRethinkDB}}

您可以使用與服務一起建立的認證，或使用服務儀表板的*概觀* 標籤中所提供的連線字串及指令行，來連接至服務。

## 將 {{site.data.keyword.cloud_notm}} 應用程式連接至 {{site.data.keyword.composeForRethinkDB}}

若要將 {{site.data.keyword.cloud_notm}} 應用程式連接至服務，請使用與服務一起建立的認證。您可以在[連接 {{site.data.keyword.cloud_notm}} 應用程式](./connecting-bluemix-app.html)中，找到如何將 {{site.data.keyword.cloud_notm}} 應用程式連接至 {{site.data.keyword.composeForRethinkDB}} 服務的資訊。

## 從 {{site.data.keyword.cloud_notm}} 之外連接至 {{site.data.keyword.composeForRethinkDB}}

如果您想要從 {{site.data.keyword.cloud_notm}} 之外連接至 {{site.data.keyword.composeForRethinkDB}}，則可以使用所提供的連線字串或指令行。您可以在[連接外部應用程式](./connecting-external.html)中，找到如何連接的相關資訊。
