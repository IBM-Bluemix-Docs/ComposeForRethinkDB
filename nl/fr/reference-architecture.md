---
copyright:
  years: 2016,2018
lastupdated: "2018-06-14"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:tip: .tip}

# Architecture 
{: #architecture}

## Réplication

Un service {{site.data.keyword.composeForRethinkDB_full}} utilise un cluster à trois noeuds de données. Lorsque vous sélectionnez une région où le service est déployé, les trois noeuds de données sont propagés dans les zones de disponibilité de la région. Les clusters RethinkDB se composent d'un membre maître qui coordonne les écritures.  Les autres membres peuvent devenir maître en cas de défaillance d'un noeud. Lorsqu'un membre de données n'est plus accessible, votre cluster continue à fonctionner normalement.

### Configuration de la réplication de vos données

La réplication des données entre les noeuds n'est **pas** un processus automatique. Les données sont réparties sur le cluster en fonction du nombre répliques et de fragments de chaque table. Vous devrez configurer vos tables pour dispersion entre les fragments. Pour ce faire, il existe trois méthodes.

1. Utiliser l'interface Web de RethinkDB. L'URL de l'interface Web intégrée correspond à la chaîne de connexion _Admin_ fournie sur la page _Vue d'ensemble_ de votre service. Vous pouvez configurer ici le partitionnement et la réplication pour toutes vos tables.
2. Utiliser la commande `reconfigure` ReQL. Pour plus d'informations sur la syntaxe de `reconfigure` et son utilisation dans différents langages, voir le [guide de référence ReQL](https://www.rethinkdb.com/api/javascript/reconfigure/).
3. Programmer votre application afin de configurer la réplication à la création de la table en utilisant le paramètre facultatif _replicas_ avec `tableCreate`. Pour plus d'informations sur la syntaxe de `tableCreate` et son utilisation dans différents langages, voir le [guide de référence ReQL](https://www.rethinkdb.com/api/javascript/table_create/).

## Chiffrement de disque

Tous les services {{site.data.keyword.composeForRethinkDB}} disposent du chiffrement au repos. Vos données résident sur des serveurs où le chiffrement au niveau volume est activé. 

Etant donné que {{site.data.keyword.composeForRethinkDB}} est un service géré, les opérateurs {{site.data.keyword.cloud}} Compose peuvent voir les données. Outre le chiffrement du disque, il est recommandé de chiffrer vos informations personnelles avant de les stocker dans la base de données ou d'utiliser des extensions ou des fonctions permettant d'activer le chiffrement sur la base de données elle-même. Même si ces méthodes risquent d'avoir un impact sur la facilité d'utilisation ou les performances, il est conseillé de s'assurer que les informations personnelles sont protégées par un chiffrement.

## Mise à l'échelle automatique

Les ressources sont automatiquement mises à l'échelle en fonction de l'utilisation totale du stockage sur disque des bases de données RethinkDB. L'utilisation de la mémoire est basée sur un rapport de stockage mis à disposition de 1 sur 10. Ces ressources sont intégrées en tant qu'unités.

La mise à l'échelle automatique est conçue pour répondre aux tendances à court et moyen termes de votre base de données. Votre service est contrôlé toutes les heures et, s'il est à court d'espace disque, des unités supplémentaires sont attribuées au déploiement.

Une mise à l'échelle automatique ne réduit pas la taille des déploiements où l'utilisation du disque/de la mémoire à diminué. Les ressources mises à disposition de vos bases de données sont conservées pour les besoins ultérieurs ou jusqu'à ce que vous réduisiez manuellement votre déploiement.
{: .tip}
