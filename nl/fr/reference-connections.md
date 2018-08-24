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

# Configuration de connexion
{: #connection-configuration}

Les connexions à la base de données {{site.data.keyword.composeForRethinkDB_full}} sont gérées par un portail RethinkDB Proxy.

## Chiffrement du transport

Le portail {{site.data.keyword.composeForRethinkDB}} Proxy dispose de TLS/SSL activé et prend en charge TLS version 1.2. Le certificat du service est un certificat autosigné. Vous devrez peut-être sauvegarder une copie locale du certificat de votre service et indiquer son emplacement à votre pilote d'applications pour établir une connexion sécurisée.

## Limites de connexion

Les connexions de base de données sont limitées à 2000 connexions par portail. Lorsque la limite de connexion est dépassée, le service ne répond plus. Vous pouvez gérer les connexions à partir de votre application à l'aide de la fonction de regroupement de connexions de votre pilote.

## Délais d'attente de proxy

Le portail Proxy gère le cycle de vie des connexions entre le serveur et le client. Nous en fournissons le détail à titre de référence pour les éditeurs de routeurs et les personnes intéressées par les activités de bas niveau des connexions de base de données {{site.data.keyword.composeForRethinkDB}}.

Paramètre | Valeur | S'applique
----------|-----------|-----------
client | 5m | Lorsque le client doit accuser réception de données ou en envoyer.
connect | 4s | Lorsqu'une connexion est établie entre le proxy et le serveur.
server | 5m | Lorsque le serveur doit accuser réception de données ou en envoyer.
tunnel | 1 jour | Lorsqu'une connexion bidirectionnelle est établie entre un client et un serveur et que la connexion reste inactive dans les deux sens.
client-fin | 1h | Lorsque le client doit accuser réception de données ou en envoyer alors qu'une direction est déjà fermée.
check | 5s | En tant que vérification secondaire du délai d'attente lorsqu'une connexion est établie entre le proxy et le serveur.
{: caption="Tableau 1. Délais d'attente des portails Proxy RethinkDB" caption-side="top"}
