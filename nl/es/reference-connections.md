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

# Configuración de conexión
{: #connection-configuration}

Las conexiones de base de datos {{site.data.keyword.composeForRethinkDB_full}} están gestionadas por un portal de proxy de RethinkDB.

## Cifrado en tránsito

El portal de proxy de {{site.data.keyword.composeForRethinkDB}} tiene TLS/SSL habilitado y da soporte a TLS versión 1.2. El certificado para el servicio es un certificado firmado automáticamente. Es posible que tenga que guardar una copia local del certificado para el servicio y proporcionar su ubicación a su controlador de aplicaciones para poder realizar una conexión segura.

## Límites de conexión

Las conexiones de base de datos tienen un límite de conexión de 2000 conexiones por portal. El exceso del límite de conexión hará que el servicio no responda. Puede gestionar las conexiones desde la aplicación a través de la característica de agrupación de conexiones del controlador.

## Tiempos de espera del proxy

El portal de proxy gestiona el ciclo de vida de las conexiones entre el servidor y el cliente. Los detallamos aquí como una referencia para los escritores de controladores y otros que tienen interés en la actividad de bajo nivel de las conexiones de base de datos de {{site.data.keyword.composeForRethinkDB}}.

Valor | Valor | Se aplica
----------|-----------|-----------
cliente | 5m | Cuando se espera que el cliente reconozca o envíe datos.
connect | 4s | Cuando se realiza una conexión entre el proxy y el servidor.
servidor | 5m | Cuando se espera que el servidor reconozca o envíe datos.
tunnel | 1 día | Cuando se establece una conexión bidireccional entre un cliente y un servidor, y la conexión permanece inactiva en ambas direcciones.
client-fin | 1h | Cuando se espera que el cliente reconozca o envíe datos mientras una dirección ya está cerrada.
check | 5s | Como una comprobación de tiempo de espera secundaria, cuando se realiza una conexión entre el proxy y el servidor.
{: caption="Tabla 1. Tiempos de espera de proxy de RethinkDB" caption-side="top"}
