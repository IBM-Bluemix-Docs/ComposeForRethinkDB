---

copyright:
  years: 2017,2018
lastupdated: "2018-03-02"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# Sauvegardes
{: #backups}

Vous pouvez créer et télécharger des sauvegardes à partir de l'onglet _Backups_ de la page de gestion du tableau de bord de votre service. Vous avez le choix entre les sauvegardes quotidiennes, hebdomadaires, mensuelles et à la demande. Elles sont conservées selon la planification suivante :

Type de sauvegarde|Planification de conservation
----------|-----------
Quotidienne|Les sauvegardes quotidiennes sont conservées pendant 7 jours
Hebdomadaire|Les sauvegardes hebdomadaires sont conservées pendant 4 semaines
Mensuelle|Les sauvegardes mensuelles sont conservées pendant 3 mois
A la demande|Une seule sauvegarde à la demande est conservée. Il s'agit toujours de la dernière sauvegarde à la demande effectuée.
{: caption="Tableau 1. Planification de conservation des sauvegardes" caption-side="top"}

Les planifications de sauvegarde et les règles de conservation sont fixées. Si vous avez besoin de conserver davantage de sauvegardes que ne le permet la planification de conservation, vous devez télécharger les sauvegardes et les archiver en fonction de vos exigences métier.

## Affichage des sauvegardes existantes

Des sauvegardes quotidiennes de votre base de données sont automatiquement planifiées. Pour afficher vos sauvegardes existantes, accédez à la page de gestion du tableau de bord de votre service. 

  ![Sauvegardes](./images/rethink-backups-show.png "Liste des sauvegardes dans le tableau de bord du service")

Cliquez sur la ligne correspondante pour développer les options de chaque sauvegarde disponible.

  ![Options de sauvegarde](./images/rethink-backups-options.png "Options d'une sauvegarde.") 

### Utilisation de l'API pour afficher les sauvegardes existantes

Une liste des sauvegardes est disponible sur le noeud final `GET /2016-07/deployments/:id/backups`. L'ID d'instance de service et l'ID de déploiement du noeud final Foundation apparaissent tous les deux dans la page de vue d'ensemble du service. Par exemple :  
``` 
https://composebroker-dashboard-public.mybluemix.net/api/2016-07/instances/$INSTANCE_ID/deployments/$DEPLOYMENT_ID/backups
```  

## Création d'une sauvegarde à la demande

Outre les sauvegardes planifiées, vous pouvez créer une sauvegarde manuelle. Pour créer une sauvegarde manuelle, accédez à la page de gestion du tableau de bord de votre service et cliquez sur *Backup now*.

### Utilisation de l'API pour la création d'une sauvegarde

Envoyez une demande POST au noeud final des sauvegardes pour initier une sauvegarde manuelle : `POST /2016-07/deployments/:id/backups`. Il renvoie immédiatement l'ID de la recette et des informations sur la sauvegarde lors de son exécution. Il vous appartient de vérifier dans le noeud final des sauvegardes si la sauvegarde est terminée et de rechercher son backup_id avant de l'utiliser. Utilisez `GET /2016-07/deployments/:id/backups/`.

## Téléchargement d'une sauvegarde

Pour télécharger une sauvegarde, accédez à la page de gestion du tableau de bord de votre service et cliquez sur *Download* sur la ligne correspondant à la sauvegarde que vous voulez télécharger.

### Utilisation de l'API pour le téléchargement d'une sauvegarde

Recherchez la sauvegarde à restaurer dans la page _Backups_ de votre service et copiez le backup_id ou utilisez `GET /2016-07/deployments/:id/backups` pour rechercher une sauvegarde et son backup_id via l'API Compose. Utilisez ensuite l'élément backup_id pour trouver des informations et le lien de téléchargement concernant une sauvegarde spécifique : `GET /2016-07/deployments/:id/backups/:backup_id`.

## Contenu de sauvegarde

Les sauvegardes RethinkDB utilisent la commande `dump` de l'utilitaire de ligne de commande RethinkDB sur votre cluster de bases de données en cours d'exécution pour sauvegarder l'intégralité de votre déploiement. Elle sauvegarde le contenu des bases de données et des tables ainsi que des métadonnées. `dump` utilise certaines ressources du cluster mais ne verrouille pas vos clients et peut être exécutée sur un cluster actif. Compose fournit des sauvegardes pour des déploiements RethinkDB dans un format que la commande `rethinkdb restore` peut utiliser directement.

## Utilisation d'une sauvegarde avec une base de données locale

Etant donné que vos sauvegardes RethinkDB sont disponibles pour téléchargement, vous pouvez obtenir une instance locale opérationnelle de votre déploiement.

1. Installez [rethink](https://www.rethinkdb.com/docs/install/)
2. Installez le [pilote Python](https://www.rethinkdb.com/docs/install-drivers/python/) dans votre chemin.
3. Téléchargez votre fichier de sauvegarde compressé. Vous n'êtes pas obligé de décompresser le fichier d'archive de sauvegarde, les outils RethinkDB s'en chargent.
4. Pour lancer RethinkDB, exécutez la commande `rethinkdb` dans une fenêtre de terminal puis, dans une autre fenêtre de terminal, accédez à l'emplacement de votre de sauvegarde téléchargée et exécutez `rethinkdb restore backup.tar.gz`.

Ouvrez une fenêtre de navigateur et accédez à `locahost:8080` pour afficher l'interface utilisateur RethinkDB et vos données.

## Apport d'une sauvegarde locale dans votre service

Si vous disposez d'un fichier de sauvegarde en local que vous voulez restaurer sur {{site.data.keyword.composeForRethinkDB}}, la commande `rethinkdb restore` vous le permet.

1. Installez [rethink](https://www.rethinkdb.com/docs/install/)
2. Installez le [pilote Python](https://www.rethinkdb.com/docs/install-drivers/python/) dans votre chemin.
3. Téléchargez le certificat depuis la page *Overview* de votre service et sauvegardez-le en local sous le nom compose.cert.
4. Procédez à la restauration à partir de la sauvegarde avec la commande suivante :

  ```
  rethinkdb restore -c <host>:<port> --tls-cert compose.cert -p backup.tar.gz
  ```

Les valeurs d'hôte et de port sont indiquées dans votre chaîne de connexion, disponible sur la page *Overview* de votre service. L'élément `-p` de la commande demande les _données d'authentification_.

**Remarque :** Si vous restaurez dans un déploiement existant vous devrez sans doute utiliser `--force` pour remplacer les tables existantes.
