---
title: Azure Monitor Logs reference - MCCEventLogs
description: Reference for MCCEventLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# MCCEventLogs

 This table includes logs for cache events. Can be used for performance metrics.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Microsoft Connected Cache




## Columns

| Column | Type | Description |
| --- | --- | --- |
| CacheNodeId | string | Unique CacheNode identifier. |
| EgressMbps | real | The total data volume (MB) per second delivered including: data volume (MB) that came directly from cache (hitMbps) and data volume (MB) that Microsoft Connected Cache had to download from CDN to see the cache (missMbps). |
| HitMbps | real | Data volume (MB) per second that came directly from Microsoft Connected Cache. |
| HitRatioMbps | real | Ratio of Data volume (MB) per second that came directly from Microsoft Connected Cache(hitMbps) to The total data volume (MB) per second delivered(egressMbps). |
| Hits | int | The number of times data is found in the cache. |
| Misses | int | The number of times data is not found in the cache and had to download from CDN. |
| MissMbps | real | Data volume (MB) per second that Microsoft Connected Cache had to download from CDN to see the cache. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Timestamp (UTC) when the log was created. |
| Type | string | The name of the table |
