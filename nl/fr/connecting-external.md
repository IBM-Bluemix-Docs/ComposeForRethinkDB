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

# Connexion d'une application externe
{: #connecting-external-app}

Plusieurs moyens, qui varient selon le pilote que vous utilisez, permettent de se connecter à RethinkDB. {{site.data.keyword.composeForRethinkDB_full}} utilise une chaîne de connexion au format URI :

```
rethinkdb://[username]:[password]@[host]:[port]/
```

Vous trouverez la chaîne de connexion sur la page *Vue d'ensemble* du service {{site.data.keyword.composeForPostgreSQL}}.

## Connexion avec SSL - Applications

Actuellement et à notre connaissance, les quatre pilotes RethinkDB officiellement pris en charge (JavaScript, Python, Ruby et Java) ainsi que le pilote Go (gorethink) prennent en charge la connexion via SSL. Si vous utilisez un autre pilote qui pose problème avec les connexions SSL, vous voudrez sans doute contacter les responsables du pilote et les informer que vous voulez réellement une prise en charge de SSL pour RethinkDB.

Afin de garantir une connexion sécurisée et de vous prémunir des attaques de type "man-in-the-middle" (intercepteur), vous aurez besoin de vous approprier la clé publique de votre déploiement. Une fois en possession de cet élément et des informations de connexion (hôte, port, clé d'authentification), consultez la documentations propre au pilote pour connaître la configuration de connexion appropriée ou lisez l'article Compose [Exemples de connexion Python, Ruby, Node/Javascript et Go](https://www.compose.io/articles/rethinkdb-and-ssl-think-secure/). Si vous utilisez Rethink 2.3 et que vous voulez vous connecter sous l'identité d'un autre utilisateur, lisez l'article Compose *[Utilisation de l'authentification d'utilisateur de RethinkDB 2.3](https://compose.io/articles/using-rethinkdb-2-3s-user-authentication/)*.

Pour une prise en charge plus poussée des applications et des pilotes, voir la documentation et les communautés propres à votre langue et au pilote que votre application utilise.

- http://rethinkdb.com/api/javascript/connect/
- http://rethinkdb.com/api/python/connect/
- http://rethinkdb.com/api/ruby/connect/
- http://rethinkdb.com/api/java/connect/
- https://github.com/dancannon/gorethink#gorethink---rethinkdb-driver-for-go
