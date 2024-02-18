---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: CDBPartitionKeyRUConsumption
---


| Column | Type | Description |
|---|---|---|
| AccountName | string | The name of the Cosmos DB account containing the physical partition. |
| _BilledSize | real | The record size in bytes |
| CollectionName | string | The name of the Cosmos DB collection, which contains the partition. |
| DatabaseName | string | The name of the Cosmos DB database, which contains the partition. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| OperationName | string | The data plane operation that consumed RUs (Request Units) for this logical partition key. |
| PartitionKey | string | The logical partition key for which RU (Request Unit) consumption statistics were retrieved. |
| PartitionKeyRangeId | string | The physical partition containing the logical partition key against which the RU (Request Unit) consuming operation was issued. |
| RegionName | string | The Azure region from which statistics for this partition were retrieved. |
| RequestCharge | real | The RUs (Request Units) consumed by this request. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (in UTC) when the request against the physical partition was issued. |
| Type | string | The name of the table |
