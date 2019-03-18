---

copyright:
  years: 2017,2018
lastupdated: "2017-06-17"

subcollection: compose-for-rethinkdb

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# Connecting an external application
{: #external-app}

You can connect to RethinkDB in a number of ways, depending on which driver you are using. {{site.data.keyword.composeForRethinkDB_full}} uses a URI format connection string:

```
rethinkdb://[username]:[password]@[host]:[port]/
```

You can find your connection string on the *Overview* page of your {{site.data.keyword.composeForRethinkDB}} service.

## Connecting with SSL - Applications

All four of the officially supported RethinkDB drivers (JavaScript, Python, Ruby, and Java) and the Go driver (gorethink) support connecting with SSL. If you're using a different driver and having trouble with SSL connections, contact the driver maintainers about adding SSL support for RethinkDB.

To ensure that the connection is both secure and prevents man-in-the-middle attacks, you need the Public Key for your deployment. When you have the key and the connection information (host, port, authentication key), look at the specific driver docs for proper connection setup or look at this Compose article for [Python, Ruby, Node/Javascript, and Go connection examples](https://www.compose.io/articles/rethinkdb-and-ssl-think-secure/); if you are using Rethink 2.3 and want to connect as a different user, refer to this Compose article on *[Using RethinkDB 2.3's user authentication](https://compose.io/articles/using-rethinkdb-2-3s-user-authentication/)*.

For in-depth application and driver support, check out the appropriate documentation and communities for your specific language and the driver that your application is using.

- [JavaScript](http://rethinkdb.com/api/javascript/connect/)
- [Python](http://rethinkdb.com/api/python/connect/)
- [Ruby](http://rethinkdb.com/api/ruby/connect/)
- [Java](http://rethinkdb.com/api/java/connect/)
- [Go](https://github.com/dancannon/gorethink#gorethink---rethinkdb-driver-for-go)
