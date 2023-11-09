---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.MachineLearningServices/workspaces/onlineEndpoints, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Connections Active**<p><p>The total number of concurrent TCP connections active from clients. |`ConnectionsActive` |Count |Average |\<none\>|PT1M |No|
|**Data Collection Errors Per Minute**<p><p>The number of data collection events dropped per minute. |`DataCollectionErrorsPerMinute` |Count |Minimum, Maximum, Average |`deployment`, `reason`, `type`|PT1M |No|
|**Data Collection Events Per Minute**<p><p>The number of data collection events processed per minute. |`DataCollectionEventsPerMinute` |Count |Minimum, Maximum, Average |`deployment`, `type`|PT1M |No|
|**Network Bytes**<p><p>The bytes per second served for the endpoint. |`NetworkBytes` |BytesPerSecond |Average |\<none\>|PT1M |No|
|**New Connections Per Second**<p><p>The average number of new TCP connections per second established from clients. |`NewConnectionsPerSecond` |CountPerSecond |Average |\<none\>|PT1M |No|
|**Request Latency**<p><p>The average complete interval of time taken for a request to be responded in milliseconds |`RequestLatency` |Milliseconds |Average |`deployment`|PT1M |Yes|
|**Request Latency P50**<p><p>The average P50 request latency aggregated by all request latency values collected over the selected time period |`RequestLatency_P50` |Milliseconds |Average |`deployment`|PT1M |Yes|
|**Request Latency P90**<p><p>The average P90 request latency aggregated by all request latency values collected over the selected time period |`RequestLatency_P90` |Milliseconds |Average |`deployment`|PT1M |Yes|
|**Request Latency P95**<p><p>The average P95 request latency aggregated by all request latency values collected over the selected time period |`RequestLatency_P95` |Milliseconds |Average |`deployment`|PT1M |Yes|
|**Request Latency P99**<p><p>The average P99 request latency aggregated by all request latency values collected over the selected time period |`RequestLatency_P99` |Milliseconds |Average |`deployment`|PT1M |Yes|
|**Requests Per Minute**<p><p>The number of requests sent to online endpoint within a minute |`RequestsPerMinute` |Count |Average |`deployment`, `statusCode`, `statusCodeClass`, `modelStatusCode`|PT1M |No|