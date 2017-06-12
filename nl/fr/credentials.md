---

copyright:
  years: 2016,2017
lastupdated: "2017-04-27"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# Données d'identification disponibles
{: #available-credentials}

Pour connecter une application à votre service, utilisez les données d'identification créées en même temps que le service. 
Le modèle d'application [compose-rethinkdb-helloworld-nodejs](https://github.com/IBM-Bluemix/compose-rethinkdb-helloworld-nodejs) montre comment utiliser Node.js pour établir une connexion au service
{{site.data.keyword.composeForRethinkDB}} à l'aide des données d'identification.

Nom de zone|Description
----------|-----------
`uri`|URI à utiliser pour établir la connexion au service. Comprend le schéma (rethinkdb:), le nom et le mot de passe de l'administrateur, le nom d'hôte du serveur et le numéro de port auquel se connecter.
`uri_admin`|URI qui doit être consulté dans un navigateur pour pouvoir accéder à l'interface d'administration de la base de données. Cet accès requiert le nom et le mot de passe de l'administrateur indiqués dans la zone `uri`.
`ca_certificate_base64`|Certificat autosigné utilisé pour confirmer qu'une application se connecte au serveur approprié. Le certificat est codé en base64. Vous devez décoder la clé avant de l'utiliser, comme illustré dans le modèle d'application.
`deployment_id`|Identificateur interne du service, créé dans Compose.
`db_type`|Type de base de données fourni par le service, en l'occurrence, `rethink`.
`name`|Nom du déploiement de base de données.
{: caption="Tableau 1. Données d'identification Compose for RethinkDB" caption-side="top"}
