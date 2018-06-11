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

# A propos de {{site.data.keyword.composeForRethinkDB}}
{: #about-compose-for-rethinkdb}

{{site.data.keyword.composeForRethinkDB_full}} fournit une base de données répartie basée sur un document JSON avec une console d'administration et d'exploration. RethinkDB utilise le langage d'interrogation ReQL, construit autour d'un chaînage de fonctions et disponible dans des bibliothèques client pour Java, JavaScript, Python et Ruby. ReQL permet d'utiliser des fonctions côté serveur RethinkDB, par exemple, des jointures et des sous-requêtes réparties sur les noeuds du cluster. En outre, RethinkDB prend en charge des index secondaires permettant d'améliorer les performances des requêtes de lecture. La fonction la plus puissante de RethinkDB, changefeeds, permet de convertir un grand nombre de requêtes ReQL en flux en temps réel.
{:shortdesc}

**Remarque :** les instances de service Compose qui ont été mises à disposition avant le 14 septembre 2016 et qui sont toujours actives peuvent encore être utilisées et sont directement accessibles sur le site [https://www.compose.com/](https://www.compose.com). Les instances de service Compose mises à disposition depuis cette date sont directement accessibles et utilisables dans votre compte {{site.data.keyword.cloud}}.

## Création d'une instance de service {{site.data.keyword.composeForRethinkDB}}

Vous pouvez créer un service {{site.data.keyword.composeForRethinkDB}} à partir de la [page {{site.data.keyword.composeForRethinkDB}}](https://console.{DomainName}/catalog/services/compose-for-rethinkdb/) du catalogue {{site.data.keyword.cloud_notm}}.

Choisissez un nom de service ainsi qu'une région, une organisation et un espace dans lesquels mettre le service à disposition. Vous pouvez utiliser la zone **Select a database version** pour sélectionner parmi les versions de base de données disponibles.

Lorsque vous mettez votre instance {{site.data.keyword.composeForRethinkDB}} à disposition, vous avez le choix entre le plan *Standard* et le plan *Entreprise*. Avec le plan *Entreprise*, vous pouvez mettre votre instance {{site.data.keyword.composeForRethinkDB}} à disposition dans un cluster {{site.data.keyword.composeEnterprise}} disponible. {{site.data.keyword.composeEnterprise}} offre la sécurité et l'isolement requis par les normes de conformité des entreprises et utilise un réseau dédié pour garantir les performances des bases de données déployées. Pour plus d'informations, voir la [documentation Compose - Entreprise](../ComposeEnterprise/index.html).

## Gestion de {{site.data.keyword.composeForRethinkDB}}

Vous pouvez gérer votre service depuis son tableau de bord. Vous y trouverez des informations concernant la base de données Compose d'{{site.data.keyword.cloud_notm}} et la manière de vous y connecter. Vous pouvez également :
- gérer vos sauvegardes ;
- allouer plus de ressources à votre service ;
- modifier le mot de passe du service ;
- constituer des listes blanches pour limiter l'accès à vos bases de données. 

Pour plus d'informations, voir [Paramètres](./dashboard-settings.html).

{{site.data.keyword.composeForRethinkDB}} repose sur les rôles Cloud Foundry pour la gestion de l'accès au service. Seuls les utilisateurs dotés du rôle Développeur peuvent voir ou utiliser le tableau de bord du service. Pour plus d'informations sur les rôles Cloud Foundry, voir les pages [Accès Cloud Foundry](https://console.bluemix.net/docs/iam/cfaccess.html#cfaccess) et [Gestion de l'accès Cloud Foundry](https://console.bluemix.net/docs/iam/mngcf.html#mngcf).
{: .tip}

## Connexion à {{site.data.keyword.composeForRethinkDB}}

Vous pouvez vous connecter à votre service avec les données d'identification créées en même temps que le service ou avec les chaînes de connexion et la ligne de commande fournies dans l'onglet *Vue d'ensemble* du tableau de bord de votre service.

## Connexion d'une application {{site.data.keyword.cloud_notm}} à {{site.data.keyword.composeForRethinkDB}}

Pour connecter une application {{site.data.keyword.cloud_notm}} à votre service, utilisez les données d'identification créées en même temps que le service. Pour plus d'informations sur la connexion d'une application {{site.data.keyword.cloud_notm}} à un service {{site.data.keyword.composeForRethinkDB}}, voir [Connexion d'une application {{site.data.keyword.cloud_notm}}](./connecting-bluemix-app.html).

## Connexion à {{site.data.keyword.composeForRethinkDB}} depuis l'extérieur d'{{site.data.keyword.cloud_notm}}

Pour vous connecter à {{site.data.keyword.composeForRethinkDB}} depuis l'extérieur d'{{site.data.keyword.cloud_notm}}, vous pouvez utiliser les chaînes de connexion ou la ligne de commande fournies. Pour plus d'informations sur ce type de connexion, voir [Connexion d'une application externe](./connecting-external.html).
