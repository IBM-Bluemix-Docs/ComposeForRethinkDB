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

# Verbindungskonfiguration
{: #connection-configuration}

{{site.data.keyword.composeForRethinkDB_full}}-Datenbankverbindungen werden von einem RethinkDB-Portal verwaltet.

## Verschlüsselung in Transit

Für das {{site.data.keyword.composeForRethinkDB}}-Proxy-Portal ist TLS/SSL aktiviert und das Portal unterstützt TLS Version 1.2. Als Zertifikat für den Service wird ein selbst signiertes Zertifikat verwendet. Möglicherweise müssen Sie eine Kopie des Zertifikats für Ihren Service lokal speichern und die Position dieser lokalen Kopie in Ihrem Anwendungstreiber angeben, um eine sichere Verbindung herstellen zu können.

## Grenzwerte für die Anzahl von Verbindungen

Für Datenbankverbindungen gilt ein Grenzwert von 2.000 Verbindungen pro Portal. Das Überschreiten des Verbindungsgrenzwerts hat zur Folge, dass Ihr Service nicht mehr reagiert. Über die Funktion Ihres Treibers für Verbindungspooling können Sie Verbindungen von ihrer Anwendung aus verwalten.

## Proxy-Zeitlimits

Das Proxy-Portal verwaltet den Lebenszyklus von Verbindungen zwischen dem Server und dem Client. Die Zeitlimitwerte sind hier als Orientierung für Treiberautoren und all diejenigen aufgeführt, die sich für die maschinennahe Aktivität von {{site.data.keyword.composeForRethinkDB}}-Datenbankverbindungen interessieren.

Einstellung | Wert | Gültigkeit
----------|-----------|-----------
client | 5 m | Wenn vom Client erwartet wird, Daten zu bestätigen oder zu senden.
connect | 4 s | Wenn eine Verbindung zwischen dem Proxy und dem Server hergestellt wird.
server | 5 m | Wenn vom Server erwartet wird, Daten zu bestätigen oder zu senden.
tunnel | 1 Tag | Wenn eine bidirektionale Verbindung zwischen einem Client und einem Server hergestellt wurde und die Verbindung in beiden Richtungen inaktiv bleibt.
client-fin | 1 h | Wenn vom Client erwartet wird, Daten zu bestätigen oder zu senden, während eine Verbindungsrichtung bereits beendet wurde.
check | 5 s | Als sekundäre Zeitlimitüberprüfung, wenn eine Verbindung zwischen dem Proxy und dem Server hergestellt wird.
{: caption="Tabelle 1. HAProxy-Zeitlimitwerte für RethinkDB" caption-side="top"}
