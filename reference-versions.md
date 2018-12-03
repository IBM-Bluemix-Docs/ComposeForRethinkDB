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

# Versions 
{: #versions}

Deployable Versions| Preferred Version
----------|-----------
2.3.6 | 2.3.6
{: caption="Table 1. RethinkDB versions" caption-side="top"}

## Preferred Version

The preferred version is typically the newest version of the RethinkDB database that is available for {{site.data.keyword.composeForRethinkDB}}. It is the version that is the default in the drop-down version selector on the catalog page. It is also the version that is automatically provisioned by API if no version is specified in the call.

### New Preferred Version Protocol

When a new version is made available, its release is announced and it is available for deployment. Following release there is an approximately 7-day window where the newest version is available, but it is not the preferred version. This window gives you a chance to deploy and test the new version, while the current version is still available. At the end of the 7-day window, the new version is set as the preferred version, or a new date for this change is announced.

The list of versions available for provisions is on the {{site.data.keyword.composeForRethinkDB}} [catalog page](https://{DomainName}/catalog/services/compose-for-rethinkdb).

To get a current list of available versions for your {{site.data.keyword.composeForRethinkDB}} service, you can use the 
[GET /2016-07/deployments/:id/versions](https://apidocs.compose.com/v1.0/reference#2016-07-get-deployments-versions) endpoint.
