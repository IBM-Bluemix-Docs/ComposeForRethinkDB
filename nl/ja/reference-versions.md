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

# バージョン 
{: #versions}

デプロイ可能バージョン| 推奨バージョン
----------|-----------
2.3.6 | 2.3.6
{: caption="表 1. RethinkDB バージョン" caption-side="top"}

## 推奨バージョン

通常、推奨バージョンは、{{site.data.keyword.composeForRethinkDB}} で使用可能な RethinkDB データベースの最新バージョンです。 このバージョンは、カタログ・ページ上のドロップダウン・バージョン・セレクターのデフォルトです。 また、API の呼び出しでバージョンを指定しない場合は、自動的にこのバージョンがプロビジョンされます。

### 新しい推奨バージョンのプロトコル

新しいバージョンが入手可能になると、そのリリースが発表され、デプロイメントで使用できるようになります。 リリース以降、最新バージョンを入手できる期間が約 7 日間ありますが、これは推奨バージョンではありません。 この期間に新しいバージョンをデプロイしたりテストしたりできますが、引き続き現行バージョンも使用できます。 この 7 日間の期間の終わりに、新しいバージョンが推奨バージョンとして設定されるか、この変更に関する新しい日付が発表されます。

プロビジョンで使用可能なバージョンのリストは、{{site.data.keyword.composeForRethinkDB}} の[カタログ・ページ](https://console.{DomainName}/catalog/services/compose-for-rethinkdb)にあります。

ご使用の {{site.data.keyword.composeForRethinkDB}} サービスで使用できるバージョンの現行リストを取得するには、
[GET /2016-07/deployments/:id/versions](https://apidocs.compose.com/v1.0/reference#2016-07-get-deployments-versions) エンドポイントを使用できます。
