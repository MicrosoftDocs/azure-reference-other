---
title: Supported metrics - Microsoft.ContainerRegistry/registries
description: Reference for Microsoft.ContainerRegistry/registries metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.ContainerRegistry/registries  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.ContainerRegistry/registries resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|AgentPool CPU Time<p><p>AgentPool CPU Time in seconds |`AgentPoolCPUTime` |Seconds |Total |No Dimensions |Yes|
|Run Duration<p><p>Run Duration in milliseconds |`RunDuration` |MilliSeconds |Total |No Dimensions |Yes|
|Storage used<p><p>The amount of storage used by the container registry. For a registry account, it's the sum of capacity used by all the repositories within a registry. It's sum of capacity used by shared layers, manifest files, and replica copies in each of its repositories. |`StorageUsed` |Bytes |Average |Geolocation |Yes|
|Successful Pull Count<p><p>Number of successful image pulls |`SuccessfulPullCount` |Count |Total |No Dimensions |Yes|
|Successful Push Count<p><p>Number of successful image pushes |`SuccessfulPushCount` |Count |Total |No Dimensions |Yes|
|Total Pull Count<p><p>Number of image pulls in total |`TotalPullCount` |Count |Total |No Dimensions |Yes|
|Total Push Count<p><p>Number of image pushes in total |`TotalPushCount` |Count |Total |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->