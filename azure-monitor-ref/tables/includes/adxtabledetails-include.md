---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: ADXTableDetails
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| CachingPolicy | dynamic | The table's effective entity caching policy, serialized as JSON |
| CachingPolicyOrigin | string | Caching policy origin entity (Table/Database/Cluster) |
| CorrelationId | string | The client request ID |
| DatabaseName | string | The name of the database |
| EntityType | string | The type of the table. Can be Table or MaterializedView |
| HotExtentCount | long | The total number of extents in the table, stored in the hot cache |
| HotExtentSize | real | The total size of extents (compressed size + index size) in the table, stored in the hot cache (in bytes) |
| HotOriginalSize | long | The total original size of data in the table, stored in the hot cache (in bytes) |
| HotRowCount | long | The total number of rows in the table, stored in the hot cache |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| MaxExtentsCreationTime | datetime | The maximum creation time of an extent in the table (or null, if there are no extents) |
| MinExtentsCreationTime | datetime | The minimum creation time of an extent in the table (or null, if there are no extents) |
| OperationName | string | The name of this operation |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RetentionPolicy | dynamic | The table's effective entity retention policy, serialized as JSON |
| RetentionPolicyOrigin | string | Retention policy origin entity (Table/Database/Cluster) |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TableName | string | The name of the table |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The time (UTC) at which this event was generated. |
| TotalExtentCount | long | The total number of extents in the table |
| TotalExtentSize | real | The total size of extents (compressed size + index size) in the table (in bytes) |
| TotalOriginalSize | real | The total original size of data in the table (in bytes) |
| TotalRowCount | long | The total number of rows in the table |
| Type | string | The name of the table |
