---
title: Supported metrics - Microsoft.MachineLearningServices/workspaces/onlineEndpoints/deployments
description: Reference for Microsoft.MachineLearningServices/workspaces/onlineEndpoints/deployments metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 08/01/2023
---
# Supported metrics for Microsoft.MachineLearningServices/workspaces/onlineEndpoints/deployments  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.MachineLearningServices/workspaces/onlineEndpoints/deployments resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|CPU Memory Utilization Percentage<p><p>Percentage of memory utilization on an instance. Utilization is reported at one minute intervals. |`CpuMemoryUtilizationPercentage` |Percent |Average |instanceId |Yes|
|CPU Utilization Percentage<p><p>Percentage of CPU utilization on an instance. Utilization is reported at one minute intervals. |`CpuUtilizationPercentage` |Percent |Average |instanceId |Yes|
|Data Collection Errors Per Minute<p><p>The number of data collection events dropped per minute. |`DataCollectionErrorsPerMinute` |Count |Average |instanceId, reason, type |No|
|Data Collection Events Per Minute<p><p>The number of data collection events processed per minute. |`DataCollectionEventsPerMinute` |Count |Average |instanceId, type |No|
|Deployment Capacity<p><p>The number of instances in the deployment. |`DeploymentCapacity` |Count |Average |instanceId, State |No|
|Disk Utilization<p><p>Percentage of disk utilization on an instance. Utilization is reported at one minute intervals. |`DiskUtilization` |Percent |Maximum |instanceId, disk |Yes|
|GPU Energy in Joules<p><p>Interval energy in Joules on a GPU node. Energy is reported at one minute intervals. |`GpuEnergyJoules` |Count |Average |instanceId |No|
|GPU Memory Utilization Percentage<p><p>Percentage of GPU memory utilization on an instance. Utilization is reported at one minute intervals. |`GpuMemoryUtilizationPercentage` |Percent |Average |instanceId |Yes|
|GPU Utilization Percentage<p><p>Percentage of GPU utilization on an instance. Utilization is reported at one minute intervals. |`GpuUtilizationPercentage` |Percent |Average |instanceId |Yes|
|Request Latency P50<p><p>The average P50 request latency aggregated by all request latency values collected over the selected time period |`RequestLatency_P50` |Milliseconds |Average |No Dimensions |Yes|
|Request Latency P90<p><p>The average P90 request latency aggregated by all request latency values collected over the selected time period |`RequestLatency_P90` |Milliseconds |Average |No Dimensions |Yes|
|Request Latency P95<p><p>The average P95 request latency aggregated by all request latency values collected over the selected time period |`RequestLatency_P95` |Milliseconds |Average |No Dimensions |Yes|
|Request Latency P99<p><p>The average P99 request latency aggregated by all request latency values collected over the selected time period |`RequestLatency_P99` |Milliseconds |Average |No Dimensions |Yes|
|Requests Per Minute<p><p>The number of requests sent to online deployment within a minute |`RequestsPerMinute` |Count |Average |envoy_response_code |No|


<!--Gen Date:  Tue Aug 01 2023 10:39:24 GMT+0300 (Israel Daylight Time)-->