---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: microsoft.avs/privateClouds, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Datastore Disk Total Capacity**<p><p>The total capacity of disk in the datastore |`CapacityLatest` |Bytes |Average |`dsname`|PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Average Effective Memory (new)**<p><p>Total available amount of machine memory in cluster |`ClusterSummaryEffectiveMemory` |Bytes |Average |`clustername`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Average Total Memory (new)**<p><p>Total memory in cluster |`ClusterSummaryTotalMemCapacityMB` |Bytes |Average |`clustername`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Percentage CPU (new)**<p><p>Percentage of Used CPU resources in Cluster |`CpuUsageAverage` |Percent |Average |`clustername`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Datastore Disk Total Capacity (new)**<p><p>The total capacity of disk in the datastore |`DiskCapacityLatest` |Bytes |Average |`dsname`|PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Datastore Disk Used (new)**<p><p>The total amount of disk used in the datastore |`DiskUsedLatest` |Bytes |Average |`dsname`|PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Percentage Datastore Disk Used (new)**<p><p>Percent of available disk used in Datastore |`DiskUsedPercentage` |Percent |Average |`dsname`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Percentage CPU**<p><p>Percentage of Used CPU resources in Cluster |`EffectiveCpuAverage` |Percent |Average |`clustername`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Average Effective Memory**<p><p>Total available amount of machine memory in cluster |`EffectiveMemAverage` |Bytes |Average |`clustername`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Average Memory Overhead (new)**<p><p>Host physical memory consumed by the virtualization infrastructure |`MemOverheadAverage` |Bytes |Average |`clustername`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Average Memory Usage (new)**<p><p>Memory usage as percentage of total configured or available memory |`MemUsageAverage` |Percent |Average |`clustername`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Average Memory Overhead**<p><p>Host physical memory consumed by the virtualization infrastructure |`OverheadAverage` |Bytes |Average |`clustername`|PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Average Total Memory**<p><p>Total memory in cluster |`TotalMbAverage` |Bytes |Average |`clustername`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Average Memory Usage**<p><p>Memory usage as percentage of total configured or available memory |`UsageAverage` |Percent |Average |`clustername`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Datastore Disk Used**<p><p>The total amount of disk used in the datastore |`UsedLatest` |Bytes |Average |`dsname`|PT30M, PT1H, PT6H, PT12H, P1D |Yes|