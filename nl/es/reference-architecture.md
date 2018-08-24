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

# Arquitectura 
{: #architecture}

## Réplica

Un servicio de {{site.data.keyword.composeForRethinkDB_full}} utiliza un clúster con tres nodos de datos. Cuando selecciona una región en la que se despliega el servicio, los tres nodos se dispersan en las zonas de disponibilidad de la región. Los clústeres de RethinkDB constan de un miembro maestro que coordinará las escrituras.  Los miembros adicionales pueden convertirse en maestro en el caso de que se produzca un error de nodo. Si un miembro de datos se vuelve inaccesible, el clúster seguirá funcionando de forma normal.

### Configuración de la réplica de los datos

La réplica de los datos en los nodos **no** es un proceso automático. Los datos se dispersan en todo el clúster basándose en la réplica y el recuento de fragmentos de cada tabla. Tiene que configurar las tablas para dispersarse en fragmentos. Hay tres maneras de hacerlo.

1. Utilice la interfaz web de RethinkDB. El URL para la interfaz web incorporada es la serie de conexión _Admin_ que se proporciona en la página _Visión general_ del servicio. Puede configurar la fragmentación y la réplica para todas las tablas de allí.
2. Utilice el mandato `reconfigure` de ReQL. Encontrará más información sobre la sintaxis de `reconfigure` con el uso en distintos idiomas en la [referencia de ReQL](https://www.rethinkdb.com/api/javascript/reconfigure/).
3. Puede programar la aplicación para configurar la réplica a la hora de crear tablas utilizando el parámetro _replicas_ opcional en `tableCreate`. Encontrará más información sobre la sintaxis de `tableCreate` con el uso en distintos idiomas en la [referencia de ReQL](https://www.rethinkdb.com/api/javascript/table_create/).

## Cifrado de disco

Todos los servicios de {{site.data.keyword.composeForRethinkDB}} tienen cifrado en reposo. Los datos residen en servidores que tienen el cifrado de nivel de volumen habilitado. 

Puesto que {{site.data.keyword.composeForRethinkDB}} es un servicio gestionado, los operadores de {{site.data.keyword.cloud}} Compose pueden ver datos. Además del cifrado de disco, le recomendamos que cifre la información personal antes de almacenarla en la base de datos o que utilice extensiones o funciones para habilitar el cifrado en la propia base de datos. Si bien estos métodos pueden afectar a la usabilidad o al rendimiento, es una buena práctica asegurarse de que la información personal esté protegida con cifrado.

## Escalado automático

Los recursos se escalan automáticamente basándose en el uso de almacenamiento de disco total de las bases de datos RethinkDB. El uso de memoria se basa en una proporción de almacenamiento suministrado en una proporción de 1:10. Estos recursos se empaquetan como unidades.

El escalado automático está diseñado para responder a las tendencias a corto y medio plazo de la base de datos. Cada hora, el servicio está marcado y si se está quedando corto en el espacio de disco, se asignan más unidades al despliegue.

El escalado automático no reduce los despliegues en los que el uso de disco/memoria se ha reducido. Los recursos suministrados a las bases de datos permanecerán para sus necesidades futuras, o hasta que reduzca el despliegue manualmente.
{: .tip}
