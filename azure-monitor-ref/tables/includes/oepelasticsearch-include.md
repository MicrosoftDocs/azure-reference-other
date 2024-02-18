---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: OEPElasticsearch
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Category | string | Logs generated as a result of operations executed using OAK APIs are grouped into categories. Categories in OAK are logical groupings based on the data source. |
| Content | string | Log details as a result of operation performed. |
| Duration | string | Time taken for performing the operation. Value is taken from 'took' property in Elasticsearch cluster as string, like '1.3ms', '478.9micros' etc. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Location | string | The region of the resource emitting the event. |
| Namespace | string | Namespace from which logs were generated, represents the data partition. |
| OperationName | string | The operation name for which the log entry was created. |
| PodName | string | Elasticsearch pod name. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Source | string | Source responsible for the log. It could be a search query or a record to be indexed in case of slow logs and null otherwise. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (in UTC) when the log was created. |
| TotalHits | string | Total number of hits for a search operation. For example, value can be '3 hits' for 3 hits, '-1' for no hits, or 'null' if it is not a search slow log. |
| Type | string | Type of log. Can be index_search_slowlog, index_indexing_slowlog, server, deprecation etc. |
