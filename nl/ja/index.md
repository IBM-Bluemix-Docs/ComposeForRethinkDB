---

copyright:
  years: 2016,2017
lastupdated: "2017-07-13"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# Compose for RethinkDB の概説
{: #getting-started-with-compose-for-rethinkdb}

{{site.data.keyword.composeForRethinkDB_full}} は、統合管理および探索コンソールを備えた、JSON 文書ベースの分散データベースを提供します。RethinkDB では ReQL 照会言語を使用します。この照会言語は、関数のチェーニングをベースに構築され、Java、JavaScript、Python、Ruby のクライアント・ライブラリーで使用できます。ReQL を使用すると、クラスターのノード間での分散結合および副照会といった、RethinkDB のサーバー・サイド機能を使用できます。また RethinkDB は、読み取り照会パフォーマンスを向上させる 2 次索引もサポートします。RethinkDB の最強機能 changefeeds を利用すると、多数の ReQL 照会をリアルタイム・フィードに変換できます。
{:shortdesc}

**注:** 2016 年 9 月 14 日より前にプロビジョンされた、現在もアクティブな Compose サービス・インスタンスは引き続き使用可能で、[https://www.compose.com/](https://www.compose.com) から直接アクセスできます。その時点以降にプロビジョンされた Compose サービス・インスタンスは、{{site.data.keyword.cloud}} アカウント内で直接アクセスして使用されます。

## Compose for RethinkDB サービス・インスタンスの作成

[{{site.data.keyword.composeForRethinkDB}} インスタンスを作成します](https://console.ng.bluemix.net/catalog/services/compose-for-rethinkdb/)。

サービスのインスタンスを作成するときは、必ずサービスの名前と資格情報名の両方を選択してください。サービスをバインドしないでおきます。サービスをプロビジョンするときに指定される資格情報を使用して、アプリケーションをサービスに接続できます。*使用可能な資格情報*セクションには、各種の資格情報値がリストされています。

{{site.data.keyword.composeForRethinkDB}} インスタンスをプロビジョンするときには、*標準*プランか*エンタープライズ*・プランを選択できます。*エンタープライズ*・プランでは、{{site.data.keyword.composeForRethinkDB}} インスタンスを利用可能な {{site.data.keyword.composeEnterprise}} クラスターにプロビジョンできます。{{site.data.keyword.composeEnterprise}} は、企業コンプライアンスで要求されるセキュリティーと分離を提供し、専用ネットワーキングを使用してデプロイ済みデータベースのパフォーマンスを確保します。詳しくは、[Compose Enterprise 文書](../ComposeEnterprise/index.html)を参照してください。

## Compose for RethinkDB の管理

サービス・ダッシュボードからサービスを管理できます。ダッシュボードには {{site.data.keyword.cloud_notm}} Compose データベースとそれへの接続方法に関する情報が示されます。また、以下の操作を行うこともできます。
- バックアップを管理する
- サービスに割り振るリソースを増やす
- サービス・パスワードを変更する
- ホワイトリストを使用してデータベースへのアクセスを制限する。
詳しくは、[設定](./dashboard-settings.html)を参照してください。

## Compose for RethinkDB への接続

サービスに接続するには、サービスと一緒に作成された資格情報を使用するか、サービス・ダッシュボードの*「概要」*タブに表示される接続ストリングとコマンド・ラインを使用します。

## {{site.data.keyword.cloud_notm}} アプリケーションの Compose for RethinkDB への接続

{{site.data.keyword.cloud_notm}} アプリケーションをサービスに接続するには、サービスと一緒に作成された資格情報を使用します。{{site.data.keyword.cloud_notm}} アプリケーションを {{site.data.keyword.composeForRethinkDB}} サービスに接続する方法については、[{{site.data.keyword.cloud_notm}} アプリケーションの接続](./connecting-bluemix-app.html)を参照してください。

## {{site.data.keyword.cloud_notm}} の外部からの Compose for RethinkDB への接続

{{site.data.keyword.composeForRethinkDB}} に {{site.data.keyword.cloud_notm}} の外部から接続するには、提供された接続ストリングまたはコマンド・ラインを使用します。接続方法については、[外部アプリケーションの接続](./connecting-external.html)を参照してください。
