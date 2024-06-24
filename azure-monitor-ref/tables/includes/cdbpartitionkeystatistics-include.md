---
ms.service: azure-monitor
ms.topic: include
ms.date: 06/24/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: CDBPartitionKeyStatistics
---


| Column | Type | Description |
|---|---|---|
| AccountName | string | The name of the Cosmos DB account containing the dataset for which partition key stats were generated. |
| _BilledSize | real | The record size in bytes |
| CollectionName | string | The name of the Cosmos DB collection, which contains��the partition. |
| DatabaseName | string | The name of the Cosmos DB database, which contains the partition. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| PartitionKey | string | The logical partition key for which storage statistics were retrieved. |
| RegionName | string | The Azure region from which statistics for this partition were retrieved. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SizeKb | int | The storage size (in KB) for the logical partition key within the physical partition. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (in UTC) when statistics for this logical partition key were generated. |
| Type | string | The name of the table |
