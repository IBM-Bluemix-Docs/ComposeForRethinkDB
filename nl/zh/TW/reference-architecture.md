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

# 架構 
{: #architecture}

## 抄寫

{{site.data.keyword.composeForRethinkDB_full}} 服務使用具有三個資料節點的叢集。當您選取部署服務的地區時，三個節點會分散在地區的可用性區域。RethinkDB 叢集包含一個協調寫入的主要成員。發生節點失效時，其他成員可以變成主要成員。萬一某一個資料成員變成無法聯繫，您的叢集將繼續正常運作。

### 設定資料的抄寫

在各節點之間抄寫資料，**不是**自動處理程序。資料會根據每個表格的抄本及 Shard 計數，分散到叢集中。您必須配置表格，以分散到各 Shard。有三種方法可以執行此作業。

1. 使用 RethinkDB Web 介面。內建 Web 介面的 URL 是服務的_概觀_ 頁面所提供的_管理_ 連線字串。您可以在該處為所有表格配置 Shard 及抄寫。
2. 使用 `reconfigure` ReQL 指令。不同語言的 `reconfigure` 語法與用法的相關資訊，提供於 [ReQL 參考資料](https://www.rethinkdb.com/api/javascript/reconfigure/)。
3. 您可以使用 `tableCreate` 的選用性 _replicas_ 參數，對應用程式進行程式設計，以在表格建立時配置抄寫。不同語言的 `tableCreate` 語法與用法的相關資訊，提供於 [ReQL 參考資料](https://www.rethinkdb.com/api/javascript/table_create/)。

## 磁碟加密

所有 {{site.data.keyword.composeForRethinkDB}} 服務都有靜態加密。您的資料位於已啟用磁區層次加密的伺服器上。 

由於 {{site.data.keyword.composeForRethinkDB}} 是一項受管理的服務，因此 {{site.data.keyword.cloud}} Compose 操作員能夠看到資料。除了磁碟加密外，我們建議您也先將個人資訊加密，再將它儲存在資料庫中，或使用延伸或特性對資料庫本身啟用加密。這些方法固然可能影響可用性或效能，確定個人資訊受到加密保護仍是個很好的作法。

## 自動調整

資源會根據 RethinkDB 資料庫的磁碟儲存空間總用量而自動調整。記憶體用量是以 1:10 的佈建儲存空間比例為基礎。這些資源組合成為單位。

自動調整的設計是要回應資料庫的中短期趨勢。每小時都會檢查您的服務，如果它的磁碟空間不足，便會將更多的單位配置給該部署。

自動調整對於磁碟/記憶體用量收縮的部署，不會將其縮減。針對您的資料庫佈建的資源將會保留以供您未來需要，或是直到您手動縮減部署為止。
{: .tip}
