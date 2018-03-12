---

copyright:
  years: 2017,2018
lastupdated: "2017-06-17"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# 連接外部應用程式
{: #connecting-external-app}

有多種方式可用來連接至 RethinkDB，視您使用的驅動程式而定。{{site.data.keyword.composeForRethinkDB_full}} 使用 URI 格式連線字串：

```
rethinkdb://[username]:[password]@[host]:[port]/
```

您將在 {{site.data.keyword.composeForPostgreSQL}} 服務的*概觀* 頁面中找到連線字串。

## 使用 SSL 連接 - 應用程式

目前就我們所知，全部四個官方支援的 RethinkDB 驅動程式（JavaScript、Python、Ruby 及 Java），以及 Go 驅動程式 (gorethink) 支援透過 SSL 進行連接。如果您使用的是不同的驅動程式，而且在使用 SSL 連線時遇到問題，您可能想要聯絡驅動程式維護人員，讓他們知道您需要 ResthkDB 支援 SSL 的程度。

若要確保連線既安全又可防止中間人攻擊，您將需要針對部署抓取「公開金鑰」。一旦在其中加上連線資訊（主機、埠、鑑別金鑰），請查看特定驅動程式的文件，以取得適當的連線設定，或查看這篇 Compose 文章，以取得 [Python、Ruby、Node/Javascript 及 Go 連線範例](https://www.compose.io/articles/rethinkdb-and-ssl-think-secure/)；如果您是使用 Rethink 2.3，而且想要以不同的使用者身分進行連接，請參閱有關*[使用 RethinkDB 2.3 的使用者鑑別](https://compose.io/articles/using-rethinkdb-2-3s-user-authentication/)* 的這篇 Compose 文章。

如需深度應用程式及驅動程式支援，請針對您的特定語言及應用程式所使用的驅動程式，查閱適當的文件和社群。

- http://rethinkdb.com/api/javascript/connect/
- http://rethinkdb.com/api/python/connect/
- http://rethinkdb.com/api/ruby/connect/
- http://rethinkdb.com/api/java/connect/
- https://github.com/dancannon/gorethink#gorethink---rethinkdb-driver-for-go
