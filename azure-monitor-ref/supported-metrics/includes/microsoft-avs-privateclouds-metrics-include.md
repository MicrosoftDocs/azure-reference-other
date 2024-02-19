---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: microsoft.avs/privateClouds, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Datastore|**Datastore Disk Total Capacity**<br><br>The total capacity of disk in the datastore |`CapacityLatest` |Bytes |Average |`dsname`|PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Cluster (new)|**Average Effective Memory (new)**<br><br>Total available amount of machine memory in cluster |`ClusterSummaryEffectiveMemory` |Bytes |Average |`clustername`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Cluster (new)|**Average Total Memory (new)**<br><br>Total memory in cluster |`ClusterSummaryTotalMemCapacityMB` |Bytes |Average |`clustername`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Cluster (new)|**Percentage CPU (new)**<br><br>Percentage of Used CPU resources in Cluster |`CpuUsageAverage` |Percent |Average |`clustername`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Datastore (new)|**Datastore Disk Total Capacity (new)**<br><br>The total capacity of disk in the datastore |`DiskCapacityLatest` |Bytes |Average |`dsname`|PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Datastore (new)|**Datastore Disk Used (new)**<br><br>The total amount of disk used in the datastore |`DiskUsedLatest` |Bytes |Average |`dsname`|PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Datastore (new)|**Percentage Datastore Disk Used (new)**<br><br>Percent of available disk used in Datastore |`DiskUsedPercentage` |Percent |Average |`dsname`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Cluster|**Percentage CPU**<br><br>Percentage of Used CPU resources in Cluster |`EffectiveCpuAverage` |Percent |Average |`clustername`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Cluster|**Average Effective Memory**<br><br>Total available amount of machine memory in cluster |`EffectiveMemAverage` |Bytes |Average |`clustername`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Cluster (new)|**Average Memory Overhead (new)**<br><br>Host physical memory consumed by the virtualization infrastructure |`MemOverheadAverage` |Bytes |Average |`clustername`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Cluster (new)|**Average Memory Usage (new)**<br><br>Memory usage as percentage of total configured or available memory |`MemUsageAverage` |Percent |Average |`clustername`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Cluster|**Average Memory Overhead**<br><br>Host physical memory consumed by the virtualization infrastructure |`OverheadAverage` |Bytes |Average |`clustername`|PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Cluster|**Average Total Memory**<br><br>Total memory in cluster |`TotalMbAverage` |Bytes |Average |`clustername`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Cluster|**Average Memory Usage**<br><br>Memory usage as percentage of total configured or available memory |`UsageAverage` |Percent |Average |`clustername`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Datastore|**Datastore Disk Used**<br><br>The total amount of disk used in the datastore |`UsedLatest` |Bytes |Average |`dsname`|PT30M, PT1H, PT6H, PT12H, P1D |Yes|