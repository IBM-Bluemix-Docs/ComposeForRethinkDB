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

# Externe Anwendung verbinden
{: #connecting-external-app}

Je nach dem verwendeten Treiber gibt es verschiedene Möglichkeiten, eine Verbindung zu RethinkDB herzustellen. {{site.data.keyword.composeForRethinkDB_full}} verwendet eine Verbindungszeichenfolge im URI-Format:

```
rethinkdb://[username]:[password]@[host]:[port]/
```

Sie finden Ihre Verbindungszeichenfolge auf der Seite *Übersicht* Ihres {{site.data.keyword.composeForPostgreSQL}}-Service.

## Verbindung mit SSL herstellen - Anwendungen

Nach heutigem Stand unterstützen alle vier offiziell unterstützten RethinkDB-Treiber (JavaScript, Python, Ruby und Java) ebenso wie der Go-Treiber (gorethink) das Herstellen einer Verbindung über SSL. Wenn Sie einen anderen Treiber verwenden und Probleme mit SSL-Verbindungen haben, wollen Sie wahrscheinlich die Treiberunterstützer kontaktieren und Ihnen mitteilen, wie viel SSL-Unterstützung für RethinkDB Sie benötigen.

Um sicherzustellen, dass die Verbindung sicher ist und Man-In-The-Middle-Angriffe verhindert, müssen Sie den öffentlichen Schlüssel für Ihre Bereitstellung abrufen. Sobald Sie diese und die Verbindungsinformationen (Host, Port, Authentifizierungsschlüssel) erhalten haben, sollten Sie zur korrekten Einrichtung der Verbindung die relevanten Treiberdokumente oder den Compose-Artikel über [Verbindungsbeispiele für Python, Ruby, Node/Javascript und Go](https://www.compose.io/articles/rethinkdb-and-ssl-think-secure/) lesen. Wenn Sie Rethink 2.3 verwenden und die Verbindung als ein anderer Benutzer herstellen wollen, finden Sie im Compose-Artikel über die *[Verwendung der Benutzerauthentifizierung von RethinkDB 2.3](https://compose.io/articles/using-rethinkdb-2-3s-user-authentication/)* weitere Informationen.

Wenn Sie eine umfassende Anwendungs- und Treiberunterstützung benötigen, informieren Sie sich in der entsprechenden Dokumentation und den Communitys Ihrer Sprache sowie über den Treiber, den Ihre Anwendung verwendet.

- http://rethinkdb.com/api/javascript/connect/
- http://rethinkdb.com/api/python/connect/
- http://rethinkdb.com/api/ruby/connect/
- http://rethinkdb.com/api/java/connect/
- https://github.com/dancannon/gorethink#gorethink---rethinkdb-driver-for-go
