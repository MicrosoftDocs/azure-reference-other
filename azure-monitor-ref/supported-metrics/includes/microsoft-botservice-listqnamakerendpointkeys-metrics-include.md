---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.BotService/listqnamakerendpointkeys, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Requests Latencies**<br><br>How long it takes to get request response |`RequestLatency` |Milliseconds |Average |`Operation`, `Authentication`, `Protocol`, `ResourceId`, `Region`|PT1M |Yes|
|**Requests Traffic**<br><br>Number of requests within a given period of time |`RequestsTraffic` |Count |Average |`Operation`, `Authentication`, `Protocol`, `ResourceId`, `Region`, `StatusCode`, `StatusCodeClass`, `StatusText`|PT1M |Yes|