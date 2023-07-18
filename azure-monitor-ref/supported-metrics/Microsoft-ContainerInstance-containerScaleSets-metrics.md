---
title: Supported metrics - Microsoft.ContainerInstance/containerScaleSets
description: Reference for Microsoft.ContainerInstance/containerScaleSets metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/17/2023
---
# Supported metrics for Microsoft.ContainerInstance/containerScaleSets  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.ContainerInstance/containerScaleSets resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Percentage CPU<p><p>Average of the CPU percentages consumed by individual Container Groups in this Scale Set |`CpuPercentage` |Percent |Average |OrchestratorId |Yes|
|CPU usage<p><p>Average of the CPU utilizations in millicores consumed by Container Groups in this Scale Set |`CpuUsage` |MilliCores |Average |OrchestratorId |Yes|
|Memory percentage<p><p>Average of the memory percentages consumed ((usedMemory/allocatedMemory) * 100) by Container Groups in this Scale Set |`MemoryPercentage` |Percent |Average |OrchestratorId |Yes|
|Memory usage<p><p>Total memory used by all the Container Groups in this Scale Set |`MemoryUsage` |Bytes |Total |OrchestratorId |Yes|


<!--Gen Date:  Mon Jul 17 2023 12:39:39 GMT+0300 (Israel Daylight Time)-->