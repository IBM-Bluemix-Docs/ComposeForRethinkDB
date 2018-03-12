---

Copyright:
  years: 2017,2018
lastupdated: "2017-10-23"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:tip: .tip}

# Navigateur de données

Le service {{site.data.keyword.composeForRethinkDB_full}} est livré avec un accès aux [outils d'administration fournis par RethinkDB](https://www.rethinkdb.com/docs/administration-tools/).

Lorsque vous sélectionnez _Navigateur de données_ un nouvel onglet s'ouvre.

Un avertissement de certificat peut s'afficher. Cet avertissement de certificat est généré car le certificat SSL du serveur est autosigné. Cliquez sur **Add Exception** pour continuer.
{: .tip}

Une boîte de dialogue de connexion s'affiche. Vous trouverez les données d'identification de connexion dans la chaîne de connexion de votre service. Le nom d'utilisateur et le mot de passe sont dans la section de la chaîne située après `rethinkdb://` et avant `@`, au format `user:password`.

Une fois connecté, vous pouvez utiliser les outils d'administration pour gérer vos données et votre cluster de bases de données Rethink. 
