---

copyright:
  years: 2017,2018
lastupdated: "2018-03-02"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# Copias de seguridad
{: #backups}

Puede crear y descargar copias de seguridad desde el separador _Copias de seguridad_ de la página _Gestionar_ del panel de control del servicio. Las copias de seguridad diarias, semanales, mensuales y bajo demanda están disponibles. Se retienen según la siguiente planificación:

Tipo de copia de seguridad|Planificación de retención
----------|-----------
Diario|Las copias de seguridad diarias se retienen durante 7 días
Semanal|Las copias de seguridad semanales se retienen durante 4 semanas
Mensual|Las copias de seguridad mensuales se retienen durante 3 meses
Bajo demanda|Se retiene una copia de seguridad bajo demanda. La copia de seguridad retenida es siempre la copia de seguridad bajo demanda más reciente.
{: caption="Tabla 1. Planificación de retención de copia de seguridad" caption-side="top"}

Las planificaciones de copia de seguridad y las políticas de retención están corregidas. Si necesita mantener más copias de seguridad de las que permite la planificación de retención, debe descargar copias de seguridad y retener archivados según sus necesidades empresariales.

## Visualización de las copias de seguridad existentes

Se planifican automáticamente copias de seguridad diarias de la base de datos. Para ver las copias de seguridad existentes, vaya a la página *Gestionar* del panel de control del servicio. 

  ![Copias de seguridad](./images/rethink-backups-show.png "Una lista de copias de seguridad del panel de control del servicio")

Pulse en la fila correspondiente para ampliar las opciones para cualquier copia de seguridad disponible.

  ![Opciones de copia de seguridad](./images/rethink-backups-options.png "Opciones de una copia de seguridad.") 

### Utilización de la API para ver las copias de seguridad existentes

Hay una lista de copias de seguridad disponible en el punto final `GET /2016-07/deployments/:id/backups`. El punto final de la fundación con el ID de la instancia de servicio y el ID de despliegue se muestran en la _Visión general_ del servicio. Por ejemplo: 
``` 
https://composebroker-dashboard-public.mybluemix.net/api/2016-07/instances/$INSTANCE_ID/deployments/$DEPLOYMENT_ID/backups
```  

## Creación de una copia de seguridad a petición

Además de copias de seguridad planificadas, puede crear una copia de seguridad manualmente. Para crear una copia de seguridad manual, vaya a la página *Gestionar* del panel de control del servicio y pulse *Copia de seguridad ahora*.

### Utilización de la API para crear una copia de seguridad

Envíe una solicitud POST al punto final de las copias de seguridad para iniciar una copia de seguridad manual: `POST /2016-07/deployments/:id/backups`. Se devuelve inmediatamente con el ID de receta e información sobre la copia de seguridad mientras está en ejecución. Es necesario comprobar el punto final de copias de seguridad para ver si la copia de seguridad ha finalizado y buscar su backup_id antes de utilizarla. Utilice `GET /2016-07/deployments/:id/backups/`.

## Descarga de una copia de seguridad

Para descargar una copia de seguridad, vaya a la página *Gestionar* del panel de control del servicio y pulse *Descargar* en la fila correspondiente a la copia de seguridad que desea descargar.

### Utilización de la API para descargar una copia de seguridad

Busque la copia de seguridad que desea restaurar en la página _Copias de seguridad_ del servicio y copie el backup_id, o utilice `GET /2016-07/deployments/:id/backups` para buscar una copia de seguridad y su backup_id mediante la API de Compose. A continuación, utilice el backup_id para buscar información y un enlace de descarga de una copia de seguridad específica: `GET /2016-07/deployments/:id/backups/:backup_id`.

## Contenido de una copia de seguridad

Las copias de seguridad de RethinkDB utilizan el mandato `dump` del programa de utilidad de línea de mandatos RethinkDB en el clúster de la base de datos en ejecución para hacer una copia de seguridad de todo el despliegue. Guarda el contenido de la base de datos y de la tabla, así como los metadatos. `dump` utiliza algunos recursos del clúster, pero no impide que los clientes accedan al mismo y se puede ejecutar en un clúster activo. Compose proporciona copias de seguridad para despliegues de RethinkDB que están en un formato que `rethinkdb restore` puede utilizar directamente.

## Utilización de una copia de seguridad con una base de datos local

Puesto que puede descargar copias de seguridad de RethinkDB, puede obtener una instancia local del despliegue configurada y en ejecución.

1. Instale [rethink](https://www.rethinkdb.com/docs/install/)
2. Instale el [controlador python](https://www.rethinkdb.com/docs/install-drivers/python/) en la vía de acceso.
3. Descargue el archivo de copia de seguridad comprimido. No es necesario que desempaquete el archivo de archivado de copia de seguridad, ya que las herramientas RethinkDB saben cómo manejarlo.
4. Para utilizar RethinkDB, ejecute el mandato `rethinkdb` en una ventana de terminal, y en otra ventana de terminal vaya a la ubicación de la copia de seguridad descargada y ejecute `rethinkdb restore backup.tar.gz`.

Abra una ventana del navegador y vaya a `locahost:8080` para ver la interfaz de usuario de RethinkDB y los datos.

## Incorporación de una copia de seguridad local al servicio

Si tiene un archivo de copia de seguridad local que desea restaurar en {{site.data.keyword.composeForRethinkDB}}, puede hacerlo con `rethinkdb restore`.

1. Instale [rethink](https://www.rethinkdb.com/docs/install/)
2. Instale el [controlador python](https://www.rethinkdb.com/docs/install-drivers/python/) en la vía de acceso.
3. Descargue el certificado desde la página *Visión general* del servicio y guárdelo localmente como compose.cert.
4. Restaure desde la copia de seguridad con el siguiente mandato:

  ```
  rethinkdb restore -c <host>:<port> --tls-cert compose.cert -p backup.tar.gz
  ```

Encontrará los valores de host y de puerto en la serie de conexión, que encontrará en la página *Visión general* del servicio. El distintivo `-p` del mandato solicitará la _credencial de autenticación_.

**Nota:** Si está restaurando en un despliegue existente, es posible que tenga que utilizar `--force` para sobrescribir las tablas existentes.
