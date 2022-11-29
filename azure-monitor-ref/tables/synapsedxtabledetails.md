---
title: Azure Monitor Logs reference - SynapseDXTableDetails
description: Reference for SynapseDXTableDetails table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# SynapseDXTableDetails

 Azure Data Explorer Synpase table details

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Synapse Workspaces




## Columns

| Column | Type | Description |
| --- | --- | --- |
| CachingPolicy | dynamic | Table's effective entity caching policy, serialized as JSON |
| CachingPolicyOrigin | string | Caching policy origin entity (Table/Database/Cluster) |
| CorrelationId | string | The client request ID |
| DatabaseName | string | Name of the database |
| HotExtentCount | long | Total number of extents in the table, stored in the hot cache |
| HotExtentSize | real | Total size of extents (compressed size + index size) in the table, stored in the hot cache (in bytes) |
| HotOriginalSize | long | Total original size of data in the table, stored in the hot cache (in bytes) |
| HotRowCount | long | Total number of rows in the table, stored in the hot cache |
| MaxExtentsCreationTime | datetime | Maximum creation time of an extent in the table (or null, if there are no extents) |
| MinExtentsCreationTime | datetime | Minimum creation time of an extent in the table (or null, if there are no extents) |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RetentionPolicy | dynamic | Table's effective entity retention policy, serialized as JSON |
| RetentionPolicyOrigin | string | Retention policy origin entity (Table/Database/Cluster) |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TableName | string | Name of the table |
| TenantId | string |  |
| TimeGenerated | datetime | The time (UTC) this event was generated |
| TotalExtentCount | long | Total number of extents in the table |
| TotalExtentSize | real | Total size of extents (compressed size + index size) in the table (in bytes) |
| TotalOriginalSize | real | The total original data size in the table (in bytes) |
| TotalRowCount | long | Total number of rows in the table |
| Type | string | The name of the table |
