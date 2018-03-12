---

copyright:
  years: 2016,2018
lastupdated: "2017-06-17"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# {{site.data.keyword.cloud_notm}}-Anwendung verbinden

Verbinden Sie eine {{site.data.keyword.cloud}}-Anwendung mit Ihrem Service mithilfe der Berechtigungsnachweise dieses Service, die bei dessen Bereitstellung erstellt werden. Die Beispielapp veranschaulicht die Verwendung von Node.js zur Herstellung einer Verbindung zu einem {{site.data.keyword.composeForRethinkDB_full}}-Service mithilfe der bereitgestellten Berechtigungsnachweise und die Vorgehensweise zur Erstellung einer Datenbank sowie Lese- und Schreibvorgänge in dieser Datenbank.

## Verbindung mithilfe der Beispielapp 'Hello World' herstellen

Die Beispielapp [compose-rethinkdb-helloworld-nodejs](https://github.com/IBM-Bluemix/compose-rethinkdb-helloworld-nodejs) veranschaulicht die Verwendung von Node.js zur Herstellung einer Verbindung zu einem {{site.data.keyword.composeForRethinkDB}}-Service mithilfe der bereitgestellten Berechtigungsnachweise. Die Anwendung erstellt eine Datenbank, liest daraus und schreibt darin.

Laden Sie die Beispielapp herunter und befolgen Sie die Anweisungen in der Readme-Datei. Anschließend klicken Sie auf der Detailseite für die Anwendung in {{site.data.keyword.cloud_notm}} auf **App anzeigen**, um den Inhalt der Tabelle *examples* anzuzeigen.

## Verfügbare Berechtigungsnachweise

Feldname|Beschreibung
----------|-----------
`uri`|Der URI, der bei der Verbindungsherstellung zum Service verwendet werden soll. Enthält das Schema (rethinkdb:), Benutzernamen und Kennwort des Administrators, den Hostnamen des Servers sowie die Nummer des Ports, zu dem die Verbindung hergestellt werden soll.
`uri_admin`|Ein URI, der in einem Browser besucht werden sollte, um Zugriff auf die Verwaltungsschnittstelle der Datenbank zu erhalten. Für den Zugriff sind Benutzername und Kennwort des Administrators aus dem Feld `uri` erforderlich.
`ca_certificate_base64`|Ein selbst signiertes Zertifikat, mit dem bestätigt wird, dass eine Anwendung eine Verbindung zum geeigneten Server herstellt. Dieses ist base64-codiert. Vor seiner Verwendung muss es decodiert werden, wie in der Beispielanwendung gezeigt.
`deployment_id`|Eine interne ID für den Service entsprechend der Erstellung in Compose.
`db_type`|Der Datenbanktyp, der vom Service angeboten wird, in diesem Fall `rethink`.
`name`|Der Name der Datenbankimplementierung.
{: caption="Tabelle 1. Compose for RethinkDB - Berechtigungsnachweise" caption-side="top"}
