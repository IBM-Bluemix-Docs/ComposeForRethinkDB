---

copyright:
  years: 2017
lastupdated: "2017-06-17"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# Conexión de una aplicación externa
{: #connecting-external-app}

En función del controlador que utilice, hay varias formas de conectarse a RethinkDB. {{site.data.keyword.composeForRethinkDB_full}} utiliza una serie de conexión con formato URI:

```
rethinkdb://[username]:[password]@[host]:[port]/
```

Encontrará su serie de conexión en la página *Visión general* del servicio {{site.data.keyword.composeForPostgreSQL}}.

## Conexión con SSL - Aplicaciones

Actualmente, por lo que sabemos, los cuatro controladores RethinkDB oficialmente soportados (JavaScript, Python, Ruby y Java), así como el controlador Go (gorethink), dan soporte a la conexión a través de SSL. Si utiliza otro controlador y tiene problemas con las conexiones SSL, quizás le interese ponerse en contacto con los responsables del mantenimiento del controlador para comunicarles que desea obtener soporte de SSL para RethinkDB.

Para garantizar que la conexión es segura y evita ataques de tipo man-in-the-middle, deberá obtener la clave pública para el despliegue. Cuando la tenga, además de la información de la conexión (host, puerto, clave de autorización), consulte la documentación del controlador específico para ver la conexión adecuada o revise este artículo de Compose sobre [Ejemplos de conexión de Python, Ruby, Node/Javascript y Go](https://www.compose.io/articles/rethinkdb-and-ssl-think-secure/); si utiliza Rethink 2.3 y desea conectarse como otro usuario, consulte este artículo de Compose sobre *[Utilización de la autenticación de usuario de RethinkDB 2.3](https://compose.io/articles/using-rethinkdb-2-3s-user-authentication/)*.

Para obtener soporte completo para la aplicación y el controlador, consulte la documentación adecuada y las comunidades correspondientes a su idioma específico y para el controlador que utiliza la aplicación.

- http://rethinkdb.com/api/javascript/connect/
- http://rethinkdb.com/api/python/connect/
- http://rethinkdb.com/api/ruby/connect/
- http://rethinkdb.com/api/java/connect/
- https://github.com/dancannon/gorethink#gorethink---rethinkdb-driver-for-go
