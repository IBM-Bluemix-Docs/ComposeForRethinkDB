---

copyright:
  years: 2017
lastupdated: "2017-06-17"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# Connessione a un'applicazione esterna
{: #connecting-external-app}

A seconda di quale driver stai utilizzando, esistono vari modi per collegarti a RethinkDB. {{site.data.keyword.composeForRethinkDB_full}} utilizza una stringa di connessione nel formato URI:

```
rethinkdb://[username]:[password]@[host]:[port]/
```

Troverai la tua stringa di connessione nella pagina *Overview* del tuo servizio {{site.data.keyword.composeForPostgreSQL}}.

## Connessione con SSL - Applicazioni

Al momento, in base alle nostre conoscenze, tutti e quattro i driver RethinkDB supportati ufficialmente (JavaScript, Python, Ruby e Java) così come il driver Go (gorethink) supportano la connessione tramite SSL. Se stai utilizzando un driver differente e hai problemi con le connessioni SSL, probabilmente vorrai contattare i responsabili del driver e fargli sapere quanto desideri il supporto SSL per RethinkDB.

Per poter garantire che la connessione sia sicura e prevenire gli attacchi MiTM (Man-in-the-Middle), dovrai prendere la chiave pubblica della tua distribuzione. Una volta che hai più informazioni sulla connessione (host, porta, chiave di autenticazione), controlla i documenti del driver specifici per una corretta configurazione della connessione o dai un'occhiata a questo articolo Compose [Python, Ruby, Node/Javascript and Go connection examples](https://www.compose.io/articles/rethinkdb-and-ssl-think-secure/); se stai utilizzando Rethink 2.3 e desideri collegarti con un riferimento utente differente a questo articolo Compose in *[Using RethinkDB 2.3's user authentication](https://compose.io/articles/using-rethinkdb-2-3s-user-authentication/)*.

Per informazioni approfondite sull'applicazione e il supporto del driver, controlla la documentazione appropriata e le comunità per il tuo linguaggio specifico e il driver che sta utilizzando la tua applicazione. 

- http://rethinkdb.com/api/javascript/connect/
- http://rethinkdb.com/api/python/connect/
- http://rethinkdb.com/api/ruby/connect/
- http://rethinkdb.com/api/java/connect/
- https://github.com/dancannon/gorethink#gorethink---rethinkdb-driver-for-go
