---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.openenergyplatform/energyservices
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [OEPAirFlowTask](/azure/azure-monitor/reference/tables/OEPAirFlowTask)<p>Diagnostic logs for AirFlow task execution having task name, task details. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/oepairflowtask)|
| [OEPAuditLogs](/azure/azure-monitor/reference/tables/OEPAuditLogs)<p>Audit Logs for Microsoft Energy Data Services. | audit, resources | LogManagement | No| -|
| [OEPDataplaneLogs](/azure/azure-monitor/reference/tables/OEPDataplaneLogs)<p>Contains logs for HTTP requests & responses for the Indexer Service API, in OSDU Data Platform, and Microsoft Energy Data Services. The Indexer service, indexes the metadata store to support search. The indexer service will automatically take items that are newly added to storage and index the attributes from the schema associated with the kind attribute. | resources | LogManagement | Yes| -|
| [OEPElasticOperator](/azure/azure-monitor/reference/tables/OEPElasticOperator)<p>Diagnostic logs for elastic operator. Elastic operator manages all the elasticsearch clusters in the oak instance. These logs can be helpful in identifing what operations are performed by the operator on the cluster. It could be upgrades, reconciliation, resource update etc. | resources | LogManagement | No| -|
| [OEPElasticsearch](/azure/azure-monitor/reference/tables/OEPElasticsearch)<p>Diagnostic logs for Elasticsearch cluster. It could be slow logs, server logs or deprecation logs. | resources | LogManagement | No| -|

  
