---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.Network/dnsResolvers, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Inbound Endpoint Count**<br><br>This metric indicates the number of inbound endpoints created for a DNS Resolver. |`InboundEndpointCount` |Count |Average, Minimum, Maximum, Count |\<none\>|PT1H, PT6H, PT12H, P1D |No|
|**Outbound Endpoint Count**<br><br>This metric indicates the number of outbound endpoints created for a DNS Resolver. |`OutboundEndpointCount` |Count |Average, Minimum, Maximum, Count |\<none\>|PT1H, PT6H, PT12H, P1D |No|
|**Queries Per Second**<br><br>This metric indicates the queries per second for a DNS Resolver. (Can be aggregated per EndpointId) |`QPS` |Count |Average, Minimum, Maximum, Count, Total |`EndpointId`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, PT24H |No|