---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: microsoft.botservice/botservices, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Request Latency<p><p>Time taken by the server to process the request |`RequestLatency` |Milliseconds |Total |Operation, Authentication, Protocol, DataCenter|PT1M |Yes|
|Requests Traffic<p><p>Number of Requests Made |`RequestsTraffic` |Percent |Count |Operation, Authentication, Protocol, StatusCode, StatusCodeClass, DataCenter|PT1M |Yes|