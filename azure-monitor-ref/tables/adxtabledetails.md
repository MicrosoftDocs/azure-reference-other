---
title: Azure Monitor Logs reference - ADXTableDetails
description: Reference for ADXTableDetails table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/8/2022
---

# ADXTableDetails

 Azure Data Explorer table details.

## Solutions

- LogManagement
## Resource types

- Azure Data Explorer Clusters




## Columns

| Column | Type | Description |
| --- | --- | --- |
| CachingPolicy | dynamic | The table's effective entity caching policy, serialized as JSON |
| CachingPolicyOrigin | string | Caching policy origin entity (Table/Database/Cluster) |
| CorrelationId | string | The client request id |
| DatabaseName | string | The name of the database |
| HotExtentCount | long | The total number of extents in the table, stored in the hot cache |
| HotExtentSize | real | The total size of extents (compressed size + index size) in the table, stored in the hot cache (in bytes) |
| HotOriginalSize | long | The total original size of data in the table, stored in the hot cache (in bytes) |
| HotRowCount | long | The total number of rows in the table, stored in the hot cache |
| MaxExtentsCreationTime | datetime | The maximum creation time of an extent in the table (or null, if there are no extents) |
| MinExtentsCreationTime | datetime | The minimum creation time of an extent in the table (or null, if there are no extents) |
| OperationName | string | The name of this operation |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RetentionPolicy | dynamic | The table's effective entity retention policy, serialized as JSON |
| RetentionPolicyOrigin | string | Retention policy origin entity (Table/Database/Cluster) |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TableName | string | The name of the table |
| TenantId | string |  |
| TimeGenerated | datetime | The time (UTC) at which this event was generated |
| TotalExtentCount | long | The total number of extents in the table |
| TotalExtentSize | real | The total size of extents (compressed size + index size) in the table (in bytes) |
| TotalOriginalSize | real | The total original size of data in the table (in bytes) |
| TotalRowCount | long | The total number of rows in the table |
| Type | string | The name of the table |
