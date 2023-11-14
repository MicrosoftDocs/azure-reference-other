---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.MachineLearningServices/workspaces/onlineEndpoints/deployments, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**CPU Memory Utilization Percentage**<p><p>Percentage of memory utilization on an instance. Utilization is reported at one minute intervals. |`CpuMemoryUtilizationPercentage` |Percent |Minimum, Maximum, Average |`instanceId`|PT1M |Yes|
|**CPU Utilization Percentage**<p><p>Percentage of CPU utilization on an instance. Utilization is reported at one minute intervals. |`CpuUtilizationPercentage` |Percent |Minimum, Maximum, Average |`instanceId`|PT1M |Yes|
|**Data Collection Errors Per Minute**<p><p>The number of data collection events dropped per minute. |`DataCollectionErrorsPerMinute` |Count |Minimum, Maximum, Average |`instanceId`, `reason`, `type`|PT1M |No|
|**Data Collection Events Per Minute**<p><p>The number of data collection events processed per minute. |`DataCollectionEventsPerMinute` |Count |Minimum, Maximum, Average |`instanceId`, `type`|PT1M |No|
|**Deployment Capacity**<p><p>The number of instances in the deployment. |`DeploymentCapacity` |Count |Minimum, Maximum, Average |`instanceId`, `State`|PT1M |No|
|**Disk Utilization**<p><p>Percentage of disk utilization on an instance. Utilization is reported at one minute intervals. |`DiskUtilization` |Percent |Minimum, Maximum, Average |`instanceId`, `disk`|PT1M |Yes|
|**GPU Energy in Joules**<p><p>Interval energy in Joules on a GPU node. Energy is reported at one minute intervals. |`GpuEnergyJoules` |Count |Minimum, Maximum, Average |`instanceId`|PT1M |No|
|**GPU Memory Utilization Percentage**<p><p>Percentage of GPU memory utilization on an instance. Utilization is reported at one minute intervals. |`GpuMemoryUtilizationPercentage` |Percent |Minimum, Maximum, Average |`instanceId`|PT1M |Yes|
|**GPU Utilization Percentage**<p><p>Percentage of GPU utilization on an instance. Utilization is reported at one minute intervals. |`GpuUtilizationPercentage` |Percent |Minimum, Maximum, Average |`instanceId`|PT1M |Yes|
|**Request Latency P50**<p><p>The average P50 request latency aggregated by all request latency values collected over the selected time period |`RequestLatency_P50` |Milliseconds |Average |\<none\>|PT1M |Yes|
|**Request Latency P90**<p><p>The average P90 request latency aggregated by all request latency values collected over the selected time period |`RequestLatency_P90` |Milliseconds |Average |\<none\>|PT1M |Yes|
|**Request Latency P95**<p><p>The average P95 request latency aggregated by all request latency values collected over the selected time period |`RequestLatency_P95` |Milliseconds |Average |\<none\>|PT1M |Yes|
|**Request Latency P99**<p><p>The average P99 request latency aggregated by all request latency values collected over the selected time period |`RequestLatency_P99` |Milliseconds |Average |\<none\>|PT1M |Yes|
|**Requests Per Minute**<p><p>The number of requests sent to online deployment within a minute |`RequestsPerMinute` |Count |Average |`envoy_response_code`|PT1M |No|