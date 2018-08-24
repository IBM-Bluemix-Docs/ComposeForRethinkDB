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

# Configurazione della connessione
{: #connection-configuration}

Le connessioni database {{site.data.keyword.composeForRethinkDB_full}} sono gestite da un portale RethinkDB Proxy.

## Crittografia in transito

Il portale {{site.data.keyword.composeForRethinkDB}} Proxy ha TLS/SSL abilitata e supporta TLS versione 1.2. Il certificato per il servizio è un certificato autofirmato. Potresti dover salvare una copia locale del certificato per il tuo servizio e fornirne l'ubicazione al driver della tua applicazione per poter creare una connessione sicura.

## Limiti connessioni

Le connessioni database hanno un limite di connessioni di 2000 connessioni per portale. Se si supera il limite di connessioni, il tuo servizio smetterà di rispondere. Puoi gestire le connessioni dalla tua applicazione tramite la funzione di pooling di connessioni del tuo driver.

## Timeout proxy

Il portale Proxy gestisce il ciclo di vita delle connessioni tra il server e il client. Li descriviamo qui in dettaglio come guida di riferimento per gli scrittori di driver e per gli altri che hanno un interesse nell'attività di basso livello delle connessioni al database {{site.data.keyword.composeForRethinkDB}}.

Impostazione | Valore | Applicazione
----------|-----------|-----------
client | 5m | Quando si prevede che il client riconosca o invii i dati.
connect | 4s | Quando si sta stabilendo una connessione tra il proxy e il server.
server | 5m | Quando si prevede che il server riconosca o invii i dati.
tunnel | 1 giorno | Quando viene stabilita una connessione bidirezionale tra un client e un server e la connessione rimane inattiva in entrambe le direzioni.
client-fin | 1o | Quando si prevede che il client riconosca o invii dati mentre una direzione è già stata arrestata.
check | 5s | Come un controllo di timeout secondario quando si sta stabilendo una connessione tra il proxy e il server.
{: caption="Tabella 1. Timeout RethinkDB Proxy" caption-side="top"}
