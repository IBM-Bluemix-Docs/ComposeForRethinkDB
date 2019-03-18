---

copyright:
  years: 2016,2018
lastupdated: "2018-03-27"

subcollection: compose-for-rethinkdb

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}

# About {{site.data.keyword.composeForRethinkDB}}
{: #about}

{{site.data.keyword.composeForRethinkDB_full}} gives you a JSON document-based, distributed database with an integrated administration and exploration console. RethinkDB uses the ReQL query language, which is built around function chaining and is available in client libraries for Java, JavaScript, Python, and Ruby. With ReQL, it is possible to use RethinkDB server-side features such as distributed joins and subqueries across the cluster’s nodes. RethinkDB also supports secondary indexes for better read query performance. RethinkDB’s most powerful feature, changefeeds, allows many ReQL queries to be converted into real-time feeds.
{:shortdesc}

**Note:** Any Compose service instances that were provisioned before 14 September 2016 that are still active can still be used and directly accessed at [https://www.compose.com/](https://www.compose.com). Any Compose service instance that is provisioned from this point forward is directly accessed and used within your {{site.data.keyword.cloud}} account.

## Creating a {{site.data.keyword.composeForRethinkDB}} service instance

You can create a {{site.data.keyword.composeForRethinkDB}} service from the [{{site.data.keyword.composeForRethinkDB}} page](https://{DomainName}/catalog/services/compose-for-rethinkdb/) in the {{site.data.keyword.cloud_notm}} catalog.

Choose a service name, and a region, organization, and space to provision the service in. You can use the **Select a database version** field to choose from the available database versions.

When you provision your {{site.data.keyword.composeForRethinkDB}} instance, you can choose the *Standard* or *Enterprise* plans. With the *Enterprise* plan, you can provision your {{site.data.keyword.composeForRethinkDB}} instance into an available {{site.data.keyword.composeEnterprise}} cluster. {{site.data.keyword.composeEnterprise}} provides the security and isolation that is required by enterprise compliance and uses dedicated networking to ensure the performance of the deployed databases. See the [{{site.data.keyword.composeEnterprise}} documentation](/docs/services/ComposeEnterprise/index.html) for more details.

## Managing {{site.data.keyword.composeForRethinkDB}}

You can manage your service from the service dashboard. Here you can find information about your {{site.data.keyword.cloud_notm}} Compose database and how to connect to it. You can also:
- Manage your backups
- Allocate more resources for your service
- Change the service password
- Use whitelists to restrict access to your databases. 

For more information, see [Settings](/docs/services/ComposeForRethinkDB?topic=compose-for-rethinkdb-dashboard-settings).

{{site.data.keyword.composeForRethinkDB}} relies on Cloud Foundry roles to manage access to the service. Only users with the Developer role can see or use the service dashboard. For more information on Cloud Foundry roles, see the [Cloud Foundry access](/docs/iam?topic=iam-cfaccess) and the [Managing Cloud Foundry access](/docs/iam?topic=iam-mngcf) pages.
{: tip}

## Connecting to {{site.data.keyword.composeForRethinkDB}}

You can connect to your service by using the credentials that are created along with the service, or with the connection strings and command line that are provided in the *Overview* tab of your service dashboard.

## Connecting an {{site.data.keyword.cloud_notm}} application to {{site.data.keyword.composeForRethinkDB}}

To connect an {{site.data.keyword.cloud_notm}} application to your service, use the credentials that are created along with the service. You can find information on how to connect an {{site.data.keyword.cloud_notm}} application to a {{site.data.keyword.composeForRethinkDB}} service in [Connecting an {{site.data.keyword.cloud_notm}} Application](/docs/services/ComposeForRethinkDB?topic=compose-for-rethinkdb-ibmcloud-cf-app).

## Connecting to {{site.data.keyword.composeForRethinkDB}} from outside {{site.data.keyword.cloud_notm}}

If you want to connect to {{site.data.keyword.composeForRethinkDB}} from outside {{site.data.keyword.cloud_notm}}, you can use the provided connection strings or command line. You can find information on how to connect in [Connecting an external application](/docs/services/ComposeForRethinkDB?topic=compose-for-rethinkdb-external-app).
