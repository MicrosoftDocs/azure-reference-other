---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Peering/peerings, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Average Customer Prefix Latency**<br><br>Average of median Customer prefix latency |`AverageCustomerPrefixLatency` |Milliseconds |Average |`RegisteredAsnName`|PT1H |Yes|
|**Egress Traffic Rate**<br><br>Egress traffic rate in bits per second |`EgressTrafficRate` |BitsPerSecond |Average |`ConnectionId`, `SessionIp`, `TrafficClass`|PT1M, PT5M, PT1H |Yes|
|**Connection Flap Events Count**<br><br>Flap Events Count in all the connection |`FlapCounts` |Count |Sum |`ConnectionId`, `SessionIp`|PT1M, PT5M, PT1H |Yes|
|**Ingress Traffic Rate**<br><br>Ingress traffic rate in bits per second |`IngressTrafficRate` |BitsPerSecond |Average |`ConnectionId`, `SessionIp`, `TrafficClass`|PT1M, PT5M, PT1H |Yes|
|**Packets Drop Rate**<br><br>Packets Drop rate in bits per second |`PacketDropRate` |BitsPerSecond |Average |`ConnectionId`, `SessionIp`, `TrafficClass`|PT1M, PT5M, PT1H |Yes|
|**Prefix Latency**<br><br>Median prefix latency |`RegisteredPrefixLatency` |Milliseconds |Average |`RegisteredPrefixName`|PT1H |Yes|
|**Session Availability**<br><br>Availability of the peering session |`SessionAvailability` |Count |Average |`ConnectionId`, `SessionIp`|PT5M, PT1H |Yes|