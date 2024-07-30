---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: SynapseDXTableDetails
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| CachingPolicy | dynamic | Table's effective entity caching policy, serialized as JSON |
| CachingPolicyOrigin | string | Caching policy origin entity (Table/Database/Cluster) |
| CorrelationId | string | The client request ID |
| DatabaseName | string | Name of the database |
| HotExtentCount | long | Total number of extents in the table, stored in the hot cache |
| HotExtentSize | real | Total size of extents (compressed size + index size) in the table, stored in the hot cache (in bytes) |
| HotOriginalSize | long | Total original size of data in the table, stored in the hot cache (in bytes) |
| HotRowCount | long | Total number of rows in the table, stored in the hot cache |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| MaxExtentsCreationTime | datetime | Maximum creation time of an extent in the table (or null, if there are no extents) |
| MinExtentsCreationTime | datetime | Minimum creation time of an extent in the table (or null, if there are no extents) |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RetentionPolicy | dynamic | Table's effective entity retention policy, serialized as JSON |
| RetentionPolicyOrigin | string | Retention policy origin entity (Table/Database/Cluster) |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TableName | string | Name of the table |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The time (UTC) this event was generated |
| TotalExtentCount | long | Total number of extents in the table |
| TotalExtentSize | real | Total size of extents (compressed size + index size) in the table (in bytes) |
| TotalOriginalSize | real | The total original data size in the table (in bytes) |
| TotalRowCount | long | Total number of rows in the table |
| Type | string | The name of the table |
