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

# Backup
{: #backups}

Puoi creare e scaricare i backup dalla scheda _Backups_ della pagina _Manage_ del tuo dashboard del servizio. Sono disponibili backup giornalieri, settimanali, mensili e su richiesta. Vengono conservati in base alla seguente pianificazione:

Tipo di backup|Pianificazione conservazione
----------|-----------
Giornaliero|I backup giornalieri sono conservati per 7 giorni
Settimanale|I backup settimanali sono conservati per 4 settimane
Mensile|I backup mensili sono conservati per 3 mesi
Su richiesta|Il backup su richiesta viene conservato. Il backup conservato è sempre il più recente backup su richiesta.
{: caption="Tabella 1. Pianificazione conservazione backup" caption-side="top"}

Le politiche di conservazione e di pianificazione del backup sono fissate. Se hai bisogno di conservare più backup rispetto a quelli consentiti dalla pianificazione di conservazione, devi scaricare i backup e conservare gli archivi in base ai tuoi requisiti di business.

## Visualizzazione dei backup esistenti

I backup giornalieri del tuo database vengono automaticamente pianificati. Per visualizzare i tuoi backup esistenti, passa alla pagina *Manage* del tuo dashboard del servizio. 

  ![Backup](./images/rethink-backups-show.png "Un elenco di backup nel dashboard del servizio")

Fai clic sulla riga corrispondente per espandere le opzioni per ogni backup disponibile.

  ![Opzioni backup](./images/rethink-backups-options.png "Opzioni per il backup.") 

### Utilizzo dell'API per visualizzare i backup esistenti

Un elenco dei backup è disponibile nell'endpoint `GET /2016-07/deployments/:id/backups`. L'endpoint fondazione, con l'ID istanza di servizio e l'ID distribuzione, sono visualizzati nella _Panoramica_ del servizio. Ad esempio: 
``` 
https://composebroker-dashboard-public.mybluemix.net/api/2016-07/instances/$INSTANCE_ID/deployments/$DEPLOYMENT_ID/backups
```  

## Creazione di un backup su richiesta

Come per i backup pianificati puoi creare un backup manualmente. Per creare un backup manuale, passa alla pagina *Manage* del tuo dashboard del servizio e fai clic su *Backup now*.

### Utilizzo dell'API per creare un backup

Invia una richiesta POST all'endpoint di backup per avviare un backup manuale: `POST /2016-07/deployments/:id/backups`. Restituisce immediatamente l'ID ricetta e le informazioni sul backup mentre è in esecuzione. Dovrai controllare l'endpoint dei backup per vedere se il backup è terminato e trovare il relativo backup_id prima di utilizzarlo. Utilizza `GET /2016-07/deployments/:id/backups/`.

## Scaricamento di un backup

Per scaricare un backup, passa alla pagina *Manage* del tuo dashboard del servizio e fai clic su *Download* nella riga corrispondente del backup che desideri scaricare.

### Utilizzo dell'API per scaricare un backup

Trova il backup da cui vuoi eseguire il ripristino nella pagina _Backups_ del tuo servizio e copia il backup_id oppure utilizza il `GET /2016-07/deployments/:id/backups` per trovare un backup e il relativo backup_id tramite l'API Compose. Utilizza quindi il backup_id per trovare le informazioni e un link di download per uno specifico backup: `GET /2016-07/deployments/:id/backups/:backup_id`.

## Contenuti del backup

I backup di RethinkDB utilizzano il comando `dump` dal programma di utilità della riga di comando RethinkDB nel tuo cluster del database in esecuzione per eseguire il backup della tua distribuzione completa. Salva i contenuti della tabella e del database così come metadati. `dump` utilizza alcune risorse cluster, ma non blocca i tuoi client e può essere eseguito in un cluster live. Compose fornisce i backup per le distribuzioni RethinkDB che sono nel formato che `rethinkdb restore` può utilizzare direttamente.

## Utilizzo di un backup con un database locale

Poiché i tuoi backup RethinkDB sono disponibili per il tuo scaricamento, puoi ottenere una istanza locale della tua distribuzione attiva e in esecuzione.

1. Installa [rethink](https://www.rethinkdb.com/docs/install/)
2. Installa il [python driver](https://www.rethinkdb.com/docs/install-drivers/python/) nel tuo percorso.
3. Scarica il tuo file di backup compresso. Non hai bisogno di decomprimere il file di archiviazione di backup, gli strumenti RethinkDB sanno come gestirlo.
4. Per avviare RethinkDB, esegui il comando `rethinkdb` in una finestra del terminale e in un'altra finestra passa all'ubicazione del tuo backup scaricato ed esegui `rethinkdb restore backup.tar.gz`.

Apri una finestra del browser e passa a `locahost:8080` per visualizzare la IU RethinkDB e i tuoi dati.

## Aggiunta di un backup locale nel tuo servizio.

Se hai un file di backup in locale che desideri ripristinare per {{site.data.keyword.composeForRethinkDB}} lo puoi fare utilizzando `rethinkdb restore`.

1. Installa [rethink](https://www.rethinkdb.com/docs/install/)
2. Installa il [python driver](https://www.rethinkdb.com/docs/install-drivers/python/) nel tuo percorso.
3. Scarica il certificato dalla pagina *Overview* del tuo servizio e salvalo localmente come compose.cert.
4. Ripristina dal backup utilizzando il seguente comando:

  ```
  rethinkdb restore -c <host>:<port> --tls-cert compose.cert -p backup.tar.gz
  ```

I valori host e porta possono essere trovati nella tua stringa di connessione, che troverai nella pagina *Overview* del tuo servizio. `-p` nel comando ti richiederà le _Credenziali di autenticazione_.

**Nota:** se stai eseguendo il ripristino in una distribuzione esistente potresti dover utilizzare `--force` per sovrascrivere le tabelle esistenti.
