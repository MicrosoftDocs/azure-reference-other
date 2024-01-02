---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Media/mediaservices/streamingEndpoints, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**CPU usage**<p><p>CPU usage for premium streaming endpoints. This data is not available for standard streaming endpoints. |`CPU` |Percent |Average, Minimum, Maximum |\<none\>|PT1M |Yes|
|**Egress**<p><p>The amount of Egress data, in bytes. |`Egress` |Bytes |Total |`OutputFormat`|PT1M |Yes|
|**Egress bandwidth**<p><p>Egress bandwidth in bits per second. |`EgressBandwidth` |BitsPerSecond |Average, Minimum, Maximum |\<none\>|PT1M |No|
|**Requests**<p><p>Requests to a Streaming Endpoint. |`Requests` |Count |Total |`OutputFormat`, `HttpStatusCode`, `ErrorCode`|PT1M |Yes|
|**Success end to end Latency**<p><p>The average latency for successful requests in milliseconds. |`SuccessE2ELatency` |MilliSeconds |Average, Minimum, Maximum |`OutputFormat`|PT1M |Yes|