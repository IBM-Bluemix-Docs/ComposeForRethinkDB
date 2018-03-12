---

copyright:
  years: 2016,2018
lastupdated: "2017-06-17"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# {{site.data.keyword.cloud_notm}} アプリケーションの接続

{{site.data.keyword.cloud}} アプリケーションをサービスに接続するには、サービスがプロビジョンされた時に作成されたサービス資格情報を使用します。 サンプル・アプリケーションでは、用意されている資格情報に基づいて Node.js によって {{site.data.keyword.composeForRethinkDB_full}} サービスに接続する方法と、データベースを作成したりデータベースの読み書きを実行したりする方法を示しています。

## 「Hello World」サンプル・アプリケーションを使用した接続

[compose-rethinkdb-helloworld-nodejs](https://github.com/IBM-Bluemix/compose-rethinkdb-helloworld-nodejs) サンプル・アプリケーションでは、用意されている資格情報に基づいて Node.js によって {{site.data.keyword.composeForRethinkDB}} サービスに接続する方法を試すことができます。 このアプリケーションはデータベースを作成し、それに対して読み取りと書き込みを行います。

サンプル・アプリケーションをダウンロードし、README ファイル内の指示に従ってください。 その後、{{site.data.keyword.cloud_notm}} のアプリケーション詳細ページで**「アプリの表示」**をクリックして、*examples* 表の内容を表示してください。

## 使用可能な資格情報

フィールド名|説明
----------|-----------
`uri`|サービスに接続するときに使用する URI。 スキーマ (rethinkdb:)、管理者ユーザー名とパスワード、サーバーのホスト名、接続先のポート番号が含まれます。
`uri_admin`|データベースの管理インターフェースにアクセスするときに、ブラウザーでアクセスする必要がある URI。 アクセスには、`uri` フィールドからの管理者ユーザー名とパスワードが必要です。
`ca_certificate_base64`|アプリケーションが適切なサーバーに接続されていることを確認するために使用する自己署名証明書。 これは base64 でエンコードされています。 サンプル・アプリケーションで示されているように、鍵をデコードした後に使用する必要があります。
`deployment_id`|Compose 内で作成された、サービスの内部 ID。
`db_type`|サービスによって提供されるデータベースのタイプ。この場合は、`rethink`。
`name`|データベース・デプロイメント名。
{: caption="表 1. Compose for RethinkDB の資格情報" caption-side="top"}
