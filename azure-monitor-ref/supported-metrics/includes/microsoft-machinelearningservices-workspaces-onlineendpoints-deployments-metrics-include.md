---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.MachineLearningServices/workspaces/onlineEndpoints/deployments, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Resource|**CPU Memory Utilization Percentage**<p><p>Percentage of memory utilization on an instance. Utilization is reported at one minute intervals. |`CpuMemoryUtilizationPercentage` |Percent |Minimum, Maximum, Average |`instanceId`|PT1M |Yes|
|Resource|**CPU Utilization Percentage**<p><p>Percentage of CPU utilization on an instance. Utilization is reported at one minute intervals. |`CpuUtilizationPercentage` |Percent |Minimum, Maximum, Average |`instanceId`|PT1M |Yes|
|Resource|**Data Collection Errors Per Minute**<p><p>The number of data collection events dropped per minute. |`DataCollectionErrorsPerMinute` |Count |Minimum, Maximum, Average |`instanceId`, `reason`, `type`|PT1M |No|
|Resource|**Data Collection Events Per Minute**<p><p>The number of data collection events processed per minute. |`DataCollectionEventsPerMinute` |Count |Minimum, Maximum, Average |`instanceId`, `type`|PT1M |No|
|Resource|**Deployment Capacity**<p><p>The number of instances in the deployment. |`DeploymentCapacity` |Count |Minimum, Maximum, Average |`instanceId`, `State`|PT1M |No|
|Resource|**Disk Utilization**<p><p>Percentage of disk utilization on an instance. Utilization is reported at one minute intervals. |`DiskUtilization` |Percent |Minimum, Maximum, Average |`instanceId`, `disk`|PT1M |Yes|
|Resource|**GPU Energy in Joules**<p><p>Interval energy in Joules on a GPU node. Energy is reported at one minute intervals. |`GpuEnergyJoules` |Count |Minimum, Maximum, Average |`instanceId`|PT1M |No|
|Resource|**GPU Memory Utilization Percentage**<p><p>Percentage of GPU memory utilization on an instance. Utilization is reported at one minute intervals. |`GpuMemoryUtilizationPercentage` |Percent |Minimum, Maximum, Average |`instanceId`|PT1M |Yes|
|Resource|**GPU Utilization Percentage**<p><p>Percentage of GPU utilization on an instance. Utilization is reported at one minute intervals. |`GpuUtilizationPercentage` |Percent |Minimum, Maximum, Average |`instanceId`|PT1M |Yes|
|Traffic|**Request Latency P50**<p><p>The average P50 request latency aggregated by all request latency values collected over the selected time period |`RequestLatency_P50` |Milliseconds |Average |\<none\>|PT1M |Yes|
|Traffic|**Request Latency P90**<p><p>The average P90 request latency aggregated by all request latency values collected over the selected time period |`RequestLatency_P90` |Milliseconds |Average |\<none\>|PT1M |Yes|
|Traffic|**Request Latency P95**<p><p>The average P95 request latency aggregated by all request latency values collected over the selected time period |`RequestLatency_P95` |Milliseconds |Average |\<none\>|PT1M |Yes|
|Traffic|**Request Latency P99**<p><p>The average P99 request latency aggregated by all request latency values collected over the selected time period |`RequestLatency_P99` |Milliseconds |Average |\<none\>|PT1M |Yes|
|Traffic|**Requests Per Minute**<p><p>The number of requests sent to online deployment within a minute |`RequestsPerMinute` |Count |Average |`envoy_response_code`|PT1M |No|