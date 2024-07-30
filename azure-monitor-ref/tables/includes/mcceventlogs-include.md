---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: MCCEventLogs
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| CacheNodeId | string | Unique CacheNode identifier. |
| EgressMbps | real | The total data volume (MB) per second delivered including: data volume (MB) that came directly from cache (hitMbps) and data volume (MB) that Microsoft Connected Cache had to download from CDN to see the cache (missMbps). |
| HitMbps | real | Data volume (MB) per second that came directly from Microsoft Connected Cache. |
| HitRatioMbps | real | Ratio of Data volume (MB) per second that came directly from Microsoft Connected Cache(hitMbps) to The total data volume (MB) per second delivered(egressMbps). |
| Hits | int | The number of times data is found in the cache. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Misses | int | The number of times data is not found in the cache and had to download from CDN. |
| MissMbps | real | Data volume (MB) per second that Microsoft Connected Cache had to download from CDN to see the cache. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (UTC) when the log was created. |
| Type | string | The name of the table |
