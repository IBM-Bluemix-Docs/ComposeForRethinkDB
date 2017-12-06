---

Copyright:
  Years: 2017
lastupdated: "2017-10-23"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:tip: .tip}

# 資料瀏覽器

{{site.data.keyword.composeForRethinkDB_full}} 服務能夠存取 [RethinkDB 所提供的管理工具](https://www.rethinkdb.com/docs/administration-tools/)。

當您選取_資料瀏覽器_ 時，會開啟新的標籤。

可能會出現憑證警告。憑證警告產生的原因是伺服器的 SSL 憑證為自簽憑證。請按一下**新增異常狀況**繼續。
{: .tip}

將會出現登入對話框。您可以在服務的連線字串找到登入認證。使用者及密碼位於字串裡 `rethinkdb://` 之後且在 `@` 之前的區段，格式為 `user:password`。

登入之後，您可以使用管理工具來管理 Rethink 資料庫叢集及資料。 
