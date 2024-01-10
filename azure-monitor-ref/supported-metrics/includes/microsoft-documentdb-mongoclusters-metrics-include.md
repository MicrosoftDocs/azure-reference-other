---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.DocumentDB/mongoClusters, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Saturation|**Committed Memory percent**<p><p>Percentage of Commit Memory Limit allocated by applications on node |`CommittedMemoryPercent` |Percent |Average, Maximum, Minimum |`ServerName`|PT1M |No|
|Saturation|**CPU percent**<p><p>Percent CPU utilization on node |`CpuPercent` |Percent |Average, Maximum, Minimum |`ServerName`|PT1M |No|
|Traffic|**IOPS**<p><p>Disk IO operations per second on node |`IOPS` |Count |Average, Maximum, Minimum |`ServerName`|PT1M |Yes|
|Saturation|**Memory percent**<p><p>Percent memory utilization on node |`MemoryPercent` |Percent |Average, Maximum, Minimum |`ServerName`|PT1M |No|
|Saturation|**Storage percent**<p><p>Percent of available storage used on node |`StoragePercent` |Percent |Average, Maximum, Minimum |`ServerName`|PT1M |No|
|Saturation|**Storage used**<p><p>Quantity of available storage used on node |`StorageUsed` |Bytes |Average, Maximum, Minimum |`ServerName`|PT1M |No|