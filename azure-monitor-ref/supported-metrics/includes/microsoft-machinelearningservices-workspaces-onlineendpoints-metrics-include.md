---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.MachineLearningServices/workspaces/onlineEndpoints, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Traffic|**Connections Active**<br><br>The total number of concurrent TCP connections active from clients. |`ConnectionsActive` |Count |Average |\<none\>|PT1M |No|
|Traffic|**Data Collection Errors Per Minute**<br><br>The number of data collection events dropped per minute. |`DataCollectionErrorsPerMinute` |Count |Minimum, Maximum, Average |`deployment`, `reason`, `type`|PT1M |No|
|Traffic|**Data Collection Events Per Minute**<br><br>The number of data collection events processed per minute. |`DataCollectionEventsPerMinute` |Count |Minimum, Maximum, Average |`deployment`, `type`|PT1M |No|
|Traffic|**Network Bytes**<br><br>The bytes per second served for the endpoint. |`NetworkBytes` |BytesPerSecond |Average |\<none\>|PT1M |No|
|Traffic|**New Connections Per Second**<br><br>The average number of new TCP connections per second established from clients. |`NewConnectionsPerSecond` |CountPerSecond |Average |\<none\>|PT1M |No|
|Traffic|**Request Latency**<br><br>The average complete interval of time taken for a request to be responded in milliseconds |`RequestLatency` |Milliseconds |Average |`deployment`|PT1M |Yes|
|Traffic|**Request Latency P50**<br><br>The average P50 request latency aggregated by all request latency values collected over the selected time period |`RequestLatency_P50` |Milliseconds |Average |`deployment`|PT1M |Yes|
|Traffic|**Request Latency P90**<br><br>The average P90 request latency aggregated by all request latency values collected over the selected time period |`RequestLatency_P90` |Milliseconds |Average |`deployment`|PT1M |Yes|
|Traffic|**Request Latency P95**<br><br>The average P95 request latency aggregated by all request latency values collected over the selected time period |`RequestLatency_P95` |Milliseconds |Average |`deployment`|PT1M |Yes|
|Traffic|**Request Latency P99**<br><br>The average P99 request latency aggregated by all request latency values collected over the selected time period |`RequestLatency_P99` |Milliseconds |Average |`deployment`|PT1M |Yes|
|Traffic|**Requests Per Minute**<br><br>The number of requests sent to online endpoint within a minute |`RequestsPerMinute` |Count |Average |`deployment`, `statusCode`, `statusCodeClass`, `modelStatusCode`|PT1M |No|