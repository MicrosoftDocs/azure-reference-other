---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.BotService/listqnamakerendpointkeys, arm
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Requests Latencies<p><p>How long it takes to get request response |`RequestLatency` |Milliseconds |Average |Operation, Authentication, Protocol, ResourceId, Region|PT1M |Yes|
|Requests Traffic<p><p>Number of requests within a given period of time |`RequestsTraffic` |Count |Average |Operation, Authentication, Protocol, ResourceId, Region, StatusCode, StatusCodeClass, StatusText|PT1M |Yes|