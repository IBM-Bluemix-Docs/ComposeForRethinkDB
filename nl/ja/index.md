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

# {{site.data.keyword.composeForRethinkDB}} の概要
{: #about-compose-for-rethinkdb}

{{site.data.keyword.composeForRethinkDB_full}} は、統合管理および探索コンソールを備えた、JSON 文書ベースの分散データベースを提供します。 RethinkDB では ReQL 照会言語を使用します。この照会言語は、関数のチェーニングをベースに構築され、Java、JavaScript、Python、Ruby のクライアント・ライブラリーで使用できます。 ReQL を使用すると、クラスターのノード間での分散結合および副照会といった、RethinkDB のサーバー・サイド機能を使用できます。 また RethinkDB は、読み取り照会パフォーマンスを向上させる 2 次索引もサポートします。 RethinkDB の最強機能 changefeeds を利用すると、多数の ReQL 照会をリアルタイム・フィードに変換できます。
{:shortdesc}

**注:** 2016 年 9 月 14 日より前にプロビジョンされた、現在もアクティブな Compose サービス・インスタンスは引き続き使用可能で、[https://www.compose.com/](https://www.compose.com) から直接アクセスできます。 その時点以降にプロビジョンされた Compose サービス・インスタンスは、{{site.data.keyword.cloud}} アカウント内で直接アクセスして使用されます。

## {{site.data.keyword.composeForRethinkDB}} サービス・インスタンスの作成

{{site.data.keyword.composeForRethinkDB}} サービスは、{{site.data.keyword.cloud_notm}} カタログの [{{site.data.keyword.composeForRethinkDB}} ページ](https://console.{DomainName}/catalog/services/compose-for-rethinkdb/)から作成できます。

サービス名、およびサービスをプロビジョンする地域、組織、スペースを選択します。 **「データベースのバージョンの選択 (Select a database version)」**フィールドを使用して、データベースの使用できるバージョンを選択できます。

{{site.data.keyword.composeForRethinkDB}} インスタンスをプロビジョンするときには、*標準*プランか*エンタープライズ*・プランを選択できます。 *エンタープライズ*・プランでは、{{site.data.keyword.composeForRethinkDB}} インスタンスを利用可能な {{site.data.keyword.composeEnterprise}} クラスターにプロビジョンできます。 {{site.data.keyword.composeEnterprise}} は、企業コンプライアンスで要求されるセキュリティーと分離を提供し、専用ネットワーキングを使用してデプロイ済みデータベースのパフォーマンスを確保します。 詳しくは、[{{site.data.keyword.composeEnterprise}} 文書](/docs/services/ComposeEnterprise/index.html)を参照してください。

## {{site.data.keyword.composeForRethinkDB}} の管理

サービス・ダッシュボードからサービスを管理できます。 ダッシュボードには {{site.data.keyword.cloud_notm}} Compose データベースとそれへの接続方法に関する情報が示されます。 また、以下の操作を行うこともできます。
- バックアップを管理する
- サービスに割り振るリソースを増やす
- サービス・パスワードを変更する
- ホワイトリストを使用してデータベースへのアクセスを制限する。 

詳しくは、[設定](./dashboard-settings.html)を参照してください。

{{site.data.keyword.composeForRethinkDB}} は、Cloud Foundry の役割を利用して、サービスへのアクセスを管理します。 開発者役割を持つユーザーのみが、サービス・ダッシュボードを表示または使用できます。 Cloud Foundry の役割について詳しくは、『[Cloud Foundry アクセス権限](https://console.{DomainName}/docs/iam/cfaccess.html#cfaccess)』および 『[Cloud Foundry のアクセス権限の管理](https://console.{DomainName}/docs/iam/mngcf.html#mngcf)』のページを参照してください。
{: .tip}

## {{site.data.keyword.composeForRethinkDB}} への接続

サービスに接続するには、サービスと一緒に作成された資格情報を使用するか、サービス・ダッシュボードの*「概要」*タブに表示される接続ストリングとコマンド・ラインを使用します。

## {{site.data.keyword.composeForRethinkDB}} への {{site.data.keyword.cloud_notm}} アプリケーションの接続

{{site.data.keyword.cloud_notm}} アプリケーションをサービスに接続するには、サービスと一緒に作成された資格情報を使用します。 {{site.data.keyword.cloud_notm}} アプリケーションを {{site.data.keyword.composeForRethinkDB}} サービスに接続する方法については、[{{site.data.keyword.cloud_notm}} アプリケーションの接続](./connecting-bluemix-app.html)を参照してください。

## {{site.data.keyword.cloud_notm}} 外からの {{site.data.keyword.composeForRethinkDB}} への接続

{{site.data.keyword.composeForRethinkDB}} に {{site.data.keyword.cloud_notm}} の外部から接続するには、提供された接続ストリングまたはコマンド・ラインを使用します。 接続方法については、[外部アプリケーションの接続](./connecting-external.html)を参照してください。
