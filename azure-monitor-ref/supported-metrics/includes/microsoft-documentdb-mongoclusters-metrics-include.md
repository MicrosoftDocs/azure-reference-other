---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.DocumentDB/mongoClusters, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Saturation|**Committed Memory percent**<br><br>Percentage of Commit Memory Limit allocated by applications on node |`CommittedMemoryPercent` |Percent |Average, Maximum, Minimum |`ServerName`|PT1M |No|
|Saturation|**CPU percent**<br><br>Percent CPU utilization on node |`CpuPercent` |Percent |Average, Maximum, Minimum |`ServerName`|PT1M |No|
|Traffic|**IOPS**<br><br>Disk IO operations per second on node |`IOPS` |Count |Average, Maximum, Minimum |`ServerName`|PT1M |Yes|
|Saturation|**Memory percent**<br><br>Percent memory utilization on node |`MemoryPercent` |Percent |Average, Maximum, Minimum |`ServerName`|PT1M |No|
|Latency|**Mongo request duration**<br><br>The end-to-end duration in milliseconds of client Mongo DB requests handled by the Mongo cluster. Updated every 60 seconds. |`MongoRequestDurationMs` |Milliseconds |Average, Count, Maximum, Minimum, Total |`Authentication`, `CollectionName`, `DatabaseName`, `ErrorCode`, `Operation`, `Protocol`, `ServerName`, `StatusCode`, `StatusCodeClass`, `StatusText`|PT1M |Yes|
|Saturation|**Storage percent**<br><br>Percent of available storage used on node |`StoragePercent` |Percent |Average, Maximum, Minimum |`ServerName`|PT1M |No|
|Saturation|**Storage used**<br><br>Quantity of available storage used on node |`StorageUsed` |Bytes |Average, Maximum, Minimum |`ServerName`|PT1M |No|