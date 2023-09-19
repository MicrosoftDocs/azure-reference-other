---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Network/dnsResolvers, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Inbound Endpoint Count<p><p>This metric indicates the number of inbound endpoints created for a DNS Resolver. |`InboundEndpointCount` |Count |Average, Minimum, Maximum, Count |No Dimensions|PT1H, PT6H, PT12H, P1D |No|
|Outbound Endpoint Count<p><p>This metric indicates the number of outbound endpoints created for a DNS Resolver. |`OutboundEndpointCount` |Count |Average, Minimum, Maximum, Count |No Dimensions|PT1H, PT6H, PT12H, P1D |No|
|Queries Per Second<p><p>This metric indicates the queries per second for a DNS Resolver. (Can be aggregated per EndpointId) |`QPS` |Count |Average, Minimum, Maximum, Count, Total |EndpointId|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, PT24H |No|