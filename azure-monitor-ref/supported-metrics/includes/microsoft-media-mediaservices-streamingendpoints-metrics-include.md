---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Media/mediaservices/streamingEndpoints, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**CPU usage**<br><br>CPU usage for premium streaming endpoints. This data is not available for standard streaming endpoints. |`CPU` |Percent |Average, Minimum, Maximum |\<none\>|PT1M |Yes|
|**Egress**<br><br>The amount of Egress data, in bytes. |`Egress` |Bytes |Total |`OutputFormat`|PT1M |Yes|
|**Egress bandwidth**<br><br>Egress bandwidth in bits per second. |`EgressBandwidth` |BitsPerSecond |Average, Minimum, Maximum |\<none\>|PT1M |No|
|**Requests**<br><br>Requests to a Streaming Endpoint. |`Requests` |Count |Total |`OutputFormat`, `HttpStatusCode`, `ErrorCode`|PT1M |Yes|
|**Success end to end Latency**<br><br>The average latency for successful requests in milliseconds. |`SuccessE2ELatency` |MilliSeconds |Average, Minimum, Maximum |`OutputFormat`|PT1M |Yes|