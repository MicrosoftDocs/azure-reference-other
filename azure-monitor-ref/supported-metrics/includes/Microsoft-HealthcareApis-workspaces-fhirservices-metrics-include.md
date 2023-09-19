---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.HealthcareApis/workspaces/fhirservices, arm
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Availability<p><p>The availability rate of the service. |`Availability` |Percent |Average |No Dimensions|PT1M |Yes|
|Total Data Size<p><p>Total size of the data in the backing database, in bytes. |`TotalDataSize` |Bytes |Total |No Dimensions|PT1M |Yes|
|Total Errors<p><p>The total number of internal server errors encountered by the service. |`TotalErrors` |Count |Sum |Protocol, StatusCode, StatusCodeClass, StatusCodeText|PT1M |Yes|
|Total Latency<p><p>The response latency of the service. |`TotalLatency` |Milliseconds |Average |Protocol|PT1M |Yes|
|Total Requests<p><p>The total number of requests received by the service. |`TotalRequests` |Count |Sum |Protocol|PT1M |Yes|