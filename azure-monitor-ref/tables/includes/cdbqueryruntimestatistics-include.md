---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: CDBQueryRuntimeStatistics
---


| Column | Type | Description |
|---|---|---|
| AccountName | string | The name of the Cosmos DB account against which the query operation was issued. |
| ActivityId | string | The unique identifier (GUID) for this query operation, which can be correlating with the CDBDataPlaneRequests table for additional debugging. |
| _BilledSize | real | The record size in bytes |
| CollectionName | string | The name of the Cosmos DB container against which this query was issued. |
| DatabaseName | string | The name of the Cosmos DB database containing the Cosmos DB container against which this query was issued. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| PartitionKeyRangeId | string | The physical partition to which this query was issued. |
| QueryText | string | The query text (obfuscated by default, full query string provided upon request) for the operation. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (in UTC) when this query operation was executed. |
| Type | string | The name of the table |
