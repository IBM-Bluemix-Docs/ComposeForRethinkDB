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

# Architettura 
{: #architecture}

## Replica

Un servizio {{site.data.keyword.composeForRethinkDB_full}} utilizza un cluster con tre nodi di dati. Quando selezioni una regione in cui viene distribuito il servizio, i tre nodi vengono distribuiti alle zone di disponibilitàdella regione. I cluster RethinkDB sono formati da un membro master che coordinerà le scritture.  I membri aggiuntivi possono diventare master in caso di errore del nodo. Se un membro dei dati diventa non raggiungibile, il cluster continuerà a funzionare normalmente.

### Configurazione della replica dei tuoi dati

La replica dei tuoi dati tra i nodi **non** è un processo automatico. I dati vengono distribuiti al cluster in base alla replica e al numero di frammenti di ogni tabella. Dovrai configurare le tue tabelle per distribuire i frammenti. Esistono tre modi per farlo.

1. Utilizza l'interfaccia web RethinkDB. L'URL per l'interfaccia web integrata è la stringa di connessione _Admin_ fornita nella tua pagina _Overview_ del servizio. Lì puoi configurare la frammentazione e la replica per tutte le tue tabelle.
2. Utilizza il comando `reconfigure` ReQL. Ulteriori informazioni sulla sintassi di `reconfigure` e l'utilizzo in diversi linguaggi possono essere trovate in [ReQL reference](https://www.rethinkdb.com/api/javascript/reconfigure/).
3. Puoi programmare la tua applicazione per configurare la replica alla creazione della tabella utilizzando il parametro facoltativo _replicas_ con `tableCreate`. Ulteriori informazioni sulla sintassi di `tableCreate` e l'utilizzo in diversi linguaggi possono essere trovate in [ReQL reference](https://www.rethinkdb.com/api/javascript/table_create/).

## Crittografia del disco

Tutti i servizi {{site.data.keyword.composeForRethinkDB}} hanno la crittografia a riposo. I tuoi dati si trovano su server che hanno la crittografia a livello di volume abilitata. 

Poiché {{site.data.keyword.composeForRethinkDB}} è un servizio gestito, gli operatori {{site.data.keyword.cloud}} Compose possono visualizzare i dati. In aggiunta alla crittografia del disco, ti consigliamo di codificare le informazioni personali prima di archiviarle nel database o di utilizzare le estensioni o le funzioni per abilitare la crittografia nel database stesso. Anche se questi metodi possono influire sull'usabilità o sulle prestazioni, è buona norma assicurarsi che le informazioni personali siano protette con la crittografia.

## Scalabilità automatica

Le risorse vengono ridimensionate automaticamente in base all'utilizzo della memoria disco totale dei database RethinkDB. L'utilizzo della memoria si basa su un rapporto di memoria di cui viene eseguito il provisioning con un rapporto di 1:10. Queste risorse sono raccolte in bundle come unità.

Il ridimensionamento automatico è progettato per rispondere alle tendenze a medio e a lungo termine del tuo database. Il tuo servizio viene controllato ogni ora e, se sta esaurendo lo spazio su disco, delle ulteriori unità vengono assegnate alla distribuzione.

Il ridimensionamento automatico non riduce le distribuzioni in cui l'utilizzo di disco/memoria si è ridotto. Le risorse di cui è stato eseguito il provisioning ai tuoi database rimarranno per le tue future esigenze oppure finché non riduci manualmente la tua distribuzione.
{: .tip}
