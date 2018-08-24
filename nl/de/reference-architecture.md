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

# Architektur 
{: #architecture}

## Replikation

Ein {{site.data.keyword.composeForRethinkDB_full}}-Service verwendet einen Cluster mit drei Datenknoten. Wenn Sie eine Region auswählen, in der der Service bereitgestellt wird, werden die drei Knoten über die Verfügbarkeitszonen der Region verteilt. RethinkDB-Cluster bestehen aus einem Master-Member, das für die Koordination der Schreibvorgänge zuständig ist.  Die anderen Member können im Falle eines Knotenfehlers die Funktion des Masters übernehmen. Sollte ein Datenelement (Member) nicht mehr erreichbar sein, setzt Ihr Cluster seinen Betrieb trotzdem ordnungsgemäß fort.

### Replikation der Daten einrichten

Die knotenübergreifende Replikation Ihrer Daten ist **kein automatisch ablaufender Prozess**. Die Daten werden basierend auf der Replikat- und der Shard-Anzahl einer jeden Tabelle über den Cluster hinweg verteilt. Sie müssen Ihre Tabellen so konfigurieren, dass sie über Shards verteilt werden. Es gibt drei Möglichkeiten, dies zu tun.

1. Verwenden Sie die RethinkDB-Webschnittstelle. Die URL für die integrierte Webschnittstelle ist die _Admin_-Verbindungszeichenfolge, die auf der Seite _Übersicht_ Ihres Service angegeben ist. Dort können Sie das Sharding und die Replikation für alle Ihre Tabellen definieren.
2. Verwenden Sie den ReQL-Befehl `reconfigure`. Weitere Informationen zur Syntax von `reconfigure` mit der jeweiligen Verwendung in verschiedenen Sprachen enthält die [ReQL-Referenz](https://www.rethinkdb.com/api/javascript/reconfigure/).
3. Durch Verwendung des optionalen Parameters _replicas_ für `tableCreate` können Sie Ihre Anwendung so programmieren, dass sie die Replikation zum Zeitpunkt der Tabellenerstellung konfiguriert. Weitere Informationen zur Syntax von `tableCreate` mit der jeweiligen Verwendung in verschiedenen Sprachen enthält die [ReQL-Referenz](https://www.rethinkdb.com/api/javascript/table_create/).

## Plattenverschlüsselung

Für alle {{site.data.keyword.composeForRethinkDB}}-Services erfolgt eine Verschlüsselung im Ruhezustand. Ihre Daten befinden sich auf Servern, auf denen die Verschlüsselung auf Datenträgerebene aktiviert ist. 

Da es sich bei {{site.data.keyword.composeForRethinkDB}} um einen verwalteten Service handelt, sind Operatoren von Compose auf {{site.data.keyword.cloud}} in der Lage, Daten zu sehen. Zusätzlich zur Plattenverschlüsselung wird empfohlen, persönliche Informationen zu verschlüsseln, bevor sie in der Datenbank gespeichert werden, oder Erweiterungen oder Features zu verwenden, um die Verschlüsselung auf der Datenbank selbst zu ermöglichen. Obwohl diese Methoden den Bedienungskomfort oder die Leistung beeinträchtigen können, hat es sich bewährt, den Schutz persönlicher Informationen mit Verschlüsselung sicherzustellen.

## Automatische Skalierung

Die Ressourcen werden basierend auf der Gesamtplattenspeicherbelegung der RethinkDB-Datenbanken automatisch skaliert. Die Hauptspeicherbelegung basiert auf einem Faktor des bereitgestellten Speichers im Verhältnis von 1:10. Diese Ressourcen werden als Einheiten gebündelt.

Die automatische Skalierung ist so konzipiert, dass sie als Reaktion auf die kurz-bis mittelfristigen Trends Ihrer Datenbank erfolgt. Ihr Service wird in stündlichen Intervallen überprüft. Wenn der Plattenspeicherplatz für den Service knapp zu drohen wird, werden der Bereitstellung weitere Einheiten zugeordnet.

Bei der automatischen Skalierung wird kein Scale-down für Bereitstellungen durchgeführt, bei denen sich die Platten-/Speicherbelegung verringert hat. Die für Ihre Datenbanken bereitgestellten Ressourcen bleiben für zukünftige Anforderungen weiterhin bestehen, sofern Sie Ihre Bereitstellung nicht per Scale-down manuell nach unten skalieren.
{: .tip}
