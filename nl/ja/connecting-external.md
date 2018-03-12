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

# 外部アプリケーションの接続
{: #connecting-external-app}

使用するドライバーに応じて、いくつかの方法で RethinkDB に接続できます。 {{site.data.keyword.composeForRethinkDB_full}} は次の URI 形式の接続ストリングを使用します。

```
rethinkdb://[username]:[password]@[host]:[port]/
```

接続ストリングは {{site.data.keyword.composeForPostgreSQL}} サービスの*「概要」*ページに表示されます。

## SSL を使用した接続 - アプリケーション

現在わかっている範囲では、公式にサポートされている 4 つの RethinkDB ドライバー (JavaScript、Python、Ruby、および Java) のすべてと、Go ドライバー (gorethink) が SSL 接続をサポートします。 別のドライバーを使用していて SSL 接続に問題がある場合には、ドライバーの保守担当者に連絡し、RethinkDB の SSL サポートが必要であることを伝えてください。

接続を保護して中間者攻撃を防止するためには、デプロイメントの公開鍵を用意する必要があります。 それに加えて接続情報 (ホスト、ポート、認証鍵) を取得したら、ドライバーの資料で正しい接続セットアップを確認するか、この Compose 記事で [Python、Ruby、Node/Javascript、Go 接続の例](https://www.compose.io/articles/rethinkdb-and-ssl-think-secure/)を確認します。Rethink 2.3 を使用して別のユーザーとして接続するには、Compose の記事 *[Using RethinkDB 2.3's user authentication](https://compose.io/articles/using-rethinkdb-2-3s-user-authentication/)*を参照してください。

アプリケーションやドライバーのサポートの詳細については、アプリケーションで使用する特定の言語とドライバーについての資料やコミュニティーを参照してください。

- http://rethinkdb.com/api/javascript/connect/
- http://rethinkdb.com/api/python/connect/
- http://rethinkdb.com/api/ruby/connect/
- http://rethinkdb.com/api/java/connect/
- https://github.com/dancannon/gorethink#gorethink---rethinkdb-driver-for-go
