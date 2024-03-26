---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.documentdb/databaseaccounts
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|
| [CDBCassandraRequests](/azure/azure-monitor/reference/tables/CDBCassandraRequests)<p>This table details data plane operations, specifically for Cassandra API accounts. | resources, audit | LogManagement | Yes| -|
| [CDBControlPlaneRequests](/azure/azure-monitor/reference/tables/CDBControlPlaneRequests)<p>This table details all control plane operations executed on the account, which include modifications to the regional failover policy, indexing policy, IAM role assignments, backup/restore policies, VNet and firewall rules, private links as well as updates and deletes of the account. | resources, audit | LogManagement | Yes| -|
| [CDBDataPlaneRequests](/azure/azure-monitor/reference/tables/CDBDataPlaneRequests)<p>The DataPlaneRequests table captures every data plane operation for the Cosmos DB account. Data Plane requests are operations executed to create, update, delete or retrieve data within the account. | resources, audit | LogManagement | Yes| -|
| [CDBGremlinRequests](/azure/azure-monitor/reference/tables/CDBGremlinRequests)<p>This table details data plane operations, specifically for Graph API accounts. | resources, audit | LogManagement | Yes| -|
| [CDBMongoRequests](/azure/azure-monitor/reference/tables/CDBMongoRequests)<p>This table details data plane operations, specifically for Mongo API accounts. | resources, audit | LogManagement | Yes| -|
| [CDBPartitionKeyRUConsumption](/azure/azure-monitor/reference/tables/CDBPartitionKeyRUConsumption)<p>This table details the RU (Request Unit) consumption for logical partition keys in each region, within each of their physical partitions. This data can be used to identify hot partitions from a request volume perspective. | resources, audit | LogManagement | Yes| -|
| [CDBPartitionKeyStatistics](/azure/azure-monitor/reference/tables/CDBPartitionKeyStatistics)<p>This table provides outlier logical partition keys that have consumed more storage space than others. Statistics are based on a sub-sampling of partition keys within the collection and hence these are approximate. Partition keys that are below 1GB of storage may not show up in the reported statistics. | resources, audit | LogManagement | Yes| -|
| [CDBQueryRuntimeStatistics](/azure/azure-monitor/reference/tables/CDBQueryRuntimeStatistics)<p>This table details query operations executed against a SQL API account. By default, the query text and its parameters are obfuscated to avoid logging PII data with full text query logging available by request. | resources, audit | LogManagement | Yes| -|

  
