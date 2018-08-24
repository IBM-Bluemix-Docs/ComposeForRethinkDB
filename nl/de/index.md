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

# Informationen zu {{site.data.keyword.composeForRethinkDB}}
{: #about-compose-for-rethinkdb}

{{site.data.keyword.composeForRethinkDB_full}} bietet Ihnen eine JSON-Dokument-basierte verteilte Datenbank mit integrierter Verwaltung und einer Untersuchungskonsole. RethinkDB verwendet die ReQL-Abfragesprache, die um Funktionsketten aufgebaut ist und in Clientbibliotheken für Java, JavaScript, Python und Ruby zur Verfügung steht. Mit ReQL besteht die Möglichkeit, serverseitige Funktionen von RethinkDB wie z. B. verteilte Joins und Unterabfragen über Clusterknoten hinweg zu verwenden. RethinkDB unterstützt außerdem sekundäre Indizes für eine bessere Lese-Abfrageleistung. Die leistungsfähigste Funktion von RethinkDB, Changefeeds, ermöglicht die Umwandlung vieler ReQL-Abfragen in Echtzeit-Feeds.
{:shortdesc}

**Hinweis:** Alle Compose-Serviceinstanzen, die vor dem 14. September 2016 bereitgestellt wurden und noch aktiv sind, können weiterhin verwendet werden und sind über [https://www.compose.com/](https://www.compose.com) zugänglich. Jede Compose-Serviceinstanz, die ab diesem Punkt bereitgestellt wird, ist direkt über Ihr {{site.data.keyword.cloud}}-Konto zugänglich und kann dort verwendet werden.

## {{site.data.keyword.composeForRethinkDB}}-Serviceinstanz erstellen

Sie können einen {{site.data.keyword.composeForRethinkDB}}-Service über die [{{site.data.keyword.composeForRethinkDB}}-Seite](https://console.{DomainName}/catalog/services/compose-for-rethinkdb/) im {{site.data.keyword.cloud_notm}}-Katalog erstellen.

Wählen Sie einen Servicenamen und eine Region, eine Organisation und einen Bereich zur Bereitstellung des Service aus. Im Feld **Datenbankversion auswählen** können Sie eine der verfügbaren Datenbankversionen auswählen.

Bei der Bereitstellung Ihrer {{site.data.keyword.composeForRethinkDB}}-Instanz können Sie den Plan *Standard* oder *Enterprise* auswählen. Mit dem Plan *Enterprise* können Sie Ihre {{site.data.keyword.composeForRethinkDB}}-Instanz in einem {{site.data.keyword.composeEnterprise}}-Cluster bereitstellen. {{site.data.keyword.composeEnterprise}} stellt die für die Konformität mit Enterprise erforderliche Sicherheit und Isolation bereit und stellt mithilfe eines dedizierten Netzbetriebs die Leistung der bereitgestellten Datenbanken sicher. Weitere Details finden Sie in der Dokumentation zu [{{site.data.keyword.composeEnterprise}}](/docs/services/ComposeEnterprise/index.html).

## {{site.data.keyword.composeForRethinkDB}} verwalten

Sie können Ihren Service über das Service-Dashboard verwalten. Hier finden Sie Informationen zu Ihrer {{site.data.keyword.cloud_notm}} Compose-Datenbank und dazu, wie Sie eine Verbindung zu ihr herstellen. Außerdem können Sie:
- Ihre Sicherungen verwalten
- Ihrem Service mehr Ressourcen zuordnen
- Das Servicekennwort ändern
- Whitelists verwenden, um den Zugriff auf Ihre Datenbank zu beschränken. 

Weitere Informationen finden Sie im Abschnitt [Einstellungen](./dashboard-settings.html).

{{site.data.keyword.composeForRethinkDB}} nutzt Cloud Foundry-Rollen, um den Zugriff auf den Service zu verwalten. Nur Benutzer mit der Entwicklerrolle können das Service-Dashboard anzeigen oder verwenden. Weitere Informationen zu Cloud Foundry-Rollen finden Sie auf den Seiten [Cloud Foundry-Zugriff](https://console.{DomainName}/docs/iam/cfaccess.html#cfaccess) und [Cloud Foundry-Zugriff](https://console.{DomainName}/docs/iam/mngcf.html#mngcf) verwalten.
{: .tip}

## Verbindung zu {{site.data.keyword.composeForRethinkDB}} herstellen

Sie können mit den Berechtigungsnachweisen, die zusammen mit Ihrem Service erstellt werden, oder mithilfe der Verbindungszeichenfolgen und der Befehlszeile, die auf der Registerkarte *Übersicht* Ihres Service-Dashboards bereitgestellt werden, eine Verbindung zu dem Service herstellen.

## Verbindung von einer {{site.data.keyword.cloud_notm}}-Anwendung zu {{site.data.keyword.composeForRethinkDB}} herstellen

Um eine {{site.data.keyword.cloud_notm}}-Anwendung mit Ihrem Service zu verbinden, verwenden Sie die Berechtigungsnachweise, die zusammen mit dem Service erstellt wurden. Informationen zum Herstellen einer Verbindung von einer {{site.data.keyword.cloud_notm}}-Anwendung zu einem {{site.data.keyword.composeForRethinkDB}}-Service finden Sie im Abschnitt [{{site.data.keyword.cloud_notm}}-Anwendung verbinden](./connecting-bluemix-app.html).

## Verbindung zu {{site.data.keyword.composeForRethinkDB}} außerhalb von {{site.data.keyword.cloud_notm}} herstellen

Wenn Sie außerhalb von {{site.data.keyword.cloud_notm}} eine Verbindung zu {{site.data.keyword.composeForRethinkDB}} herstellen wollen, können Sie dazu die bereitgestellten Verbindungszeichenfolgen oder die Befehlszeile verwenden. Informationen dazu, wie sich eine Verbindung herstellen lässt, finden Sie im Abschnitt [Externe Anwendung verbinden](./connecting-external.html).
