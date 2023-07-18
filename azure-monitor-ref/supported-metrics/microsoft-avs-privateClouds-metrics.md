---
title: Supported metrics - microsoft.avs/privateClouds
description: Reference for microsoft.avs/privateClouds metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for microsoft.avs/privateClouds  
<!-- Data source : naam-->


The following table lists the metrics available for the microsoft.avs/privateClouds resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Datastore Disk Total Capacity<p><p>The total capacity of disk in the datastore |`CapacityLatest` |Bytes |Average |dsname |Yes|
| Percentage Datastore Disk Used<p><p>Percent of available disk used in Datastore |`DiskUsedPercentage` |Percent |Average |dsname |Yes|
|Percentage CPU<p><p>Percentage of Used CPU resources in Cluster |`EffectiveCpuAverage` |Percent |Average |clustername |Yes|
|Average Effective Memory<p><p>Total available amount of machine memory in cluster |`EffectiveMemAverage` |Bytes |Average |clustername |Yes|
|Average Memory Overhead<p><p>Host physical memory consumed by the virtualization infrastructure |`OverheadAverage` |Bytes |Average |clustername |Yes|
|Average Total Memory<p><p>Total memory in cluster |`TotalMbAverage` |Bytes |Average |clustername |Yes|
|Average Memory Usage<p><p>Memory usage as percentage of total configured or available memory |`UsageAverage` |Percent |Average |clustername |Yes|
|Datastore Disk Used<p><p>The total amount of disk used in the datastore |`UsedLatest` |Bytes |Average |dsname |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->