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

# Data Browser

The {{site.data.keyword.composeForRethinkDB}} service comes with access to the [administration tools provided by RethinkDB](https://www.rethinkdb.com/docs/administration-tools/).

When you select _Data Browser_ a new tab opens.

A certificate warning might appear. A certificate warning is generated because the server's SSL certificate is self-signed. Click **Add Exception** to continue.
{: .tip}

A login dialog will appear. You can find the login credentials in your service's connection string. The user and password are the section of the string after the `rethinkdb://` and before the `@`, in the format `user:password`.

When you are logged in you can use the administration tools to manage your Rethink database cluster and data. 
