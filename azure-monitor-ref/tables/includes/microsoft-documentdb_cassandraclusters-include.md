---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.documentdb/cassandraclusters
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [CassandraAudit](/azure/azure-monitor/reference/tables/CassandraAudit)<p>Detailed audit records for CQL operations and login attempts. | audit | LogManagement | No| -|
| [CassandraLogs](/azure/azure-monitor/reference/tables/CassandraLogs)<p>Cassandra general logging messages (system.log). |  | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/cassandralogs)|

  
