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

# Connecting an external application
{: #connecting-external-app}

Depending on which driver you are using, there are a number of ways to connect to RethinkDB. {{site.data.keyword.composeForRethinkDB_full}} uses a URI format connection string:

```
rethinkdb://[username]:[password]@[host]:[port]/
```

You'll find your connection string on the *Overview* page of your {{site.data.keyword.composeForPostgreSQL}} service.

## Connecting with SSL - Applications

Currently and to our knowledge, all four of the officially supported RethinkDB drivers (JavaScript, Python, Ruby and Java) as well as the Go driver (gorethink) support connecting via SSL. If you're using a different driver and having trouble with SSL connections, you'll probably want to contact the driver maintainers and let them know how much you want SSL support for RethinkDB.

In order to ensure the connection is both secure and prevents man-in-the-middle attacks, you'll need to grab the Public Key for your deployment. Once you have that plus the connection info (host, port, auth key), take a look at the specific driver docs for proper connection setup or take a look at this Compose article for [Python, Ruby, Node/Javascript and Go connection examples](https://www.compose.io/articles/rethinkdb-and-ssl-think-secure/); If you are using Rethink 2.3 and want to connect as a different user refer to this Compose article on *[Using RethinkDB 2.3's user authentication](https://compose.io/articles/using-rethinkdb-2-3s-user-authentication/)*.

For in-depth application and driver support, check out the appropriate documentation and communities for your specific language and the driver that your application is using.

- http://rethinkdb.com/api/javascript/connect/
- http://rethinkdb.com/api/python/connect/
- http://rethinkdb.com/api/ruby/connect/
- http://rethinkdb.com/api/java/connect/
- https://github.com/dancannon/gorethink#gorethink---rethinkdb-driver-for-go
