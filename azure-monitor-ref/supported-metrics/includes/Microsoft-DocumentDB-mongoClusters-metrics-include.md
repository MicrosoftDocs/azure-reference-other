---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.DocumentDB/mongoClusters, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Committed Memory percent<p><p>Percentage of Commit Memory Limit allocated by applications on node |`CommittedMemoryPercent` |Percent |Average, Maximum, Minimum |ServerName|PT1M |No|
|CPU percent<p><p>Percent CPU utilization on node |`CpuPercent` |Percent |Average, Maximum, Minimum |ServerName|PT1M |No|
|IOPS<p><p>Disk IO operations per second on node |`IOPS` |Count |Average, Maximum, Minimum |ServerName|PT1M |Yes|
|Memory percent<p><p>Percent memory utilization on node |`MemoryPercent` |Percent |Average, Maximum, Minimum |ServerName|PT1M |No|
|Storage percent<p><p>Percent of available storage used on node |`StoragePercent` |Percent |Average, Maximum, Minimum |ServerName|PT1M |No|
|Storage used<p><p>Quantity of available storage used on node |`StorageUsed` |Bytes |Average, Maximum, Minimum |ServerName|PT1M |No|