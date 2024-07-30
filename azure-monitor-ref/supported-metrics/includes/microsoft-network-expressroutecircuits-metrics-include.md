---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.Network/expressRouteCircuits, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Circuit Availability|**Arp Availability**<br><br>ARP Availability from MSEE towards all peers. |`ArpAvailability` |Percent |Average |`PeeringType`, `Peer`|PT1M |Yes|
|Circuit Availability|**Bgp Availability**<br><br>BGP Availability from MSEE towards all peers. |`BgpAvailability` |Percent |Average |`PeeringType`, `Peer`|PT1M |Yes|
|Circuit Traffic|**BitsInPerSecond**<br><br>Bits ingressing Azure per second |`BitsInPerSecond` |BitsPerSecond |Average |`PeeringType`, `DeviceRole`|PT1M |Yes|
|Circuit Traffic|**BitsOutPerSecond**<br><br>Bits egressing Azure per second |`BitsOutPerSecond` |BitsPerSecond |Average |`PeeringType`, `DeviceRole`|PT1M |Yes|
|Fastpath|**FastPathRoutesCount**<br><br>Count of fastpath routes configured on circuit |`FastPathRoutesCountForCircuit` |Count |Maximum |\<none\>|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|GlobalReach Traffic|**GlobalReachBitsInPerSecond**<br><br>Bits ingressing Azure per second |`GlobalReachBitsInPerSecond` |BitsPerSecond |Average |`PeeredCircuitSKey`|PT1M |No|
|GlobalReach Traffic|**GlobalReachBitsOutPerSecond**<br><br>Bits egressing Azure per second |`GlobalReachBitsOutPerSecond` |BitsPerSecond |Average |`PeeredCircuitSKey`|PT1M |No|
|Circuit Qos|**DroppedInBitsPerSecond**<br><br>Ingress bits of data dropped per second |`QosDropBitsInPerSecond` |BitsPerSecond |Average |\<none\>|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Circuit Qos|**DroppedOutBitsPerSecond**<br><br>Egress bits of data dropped per second |`QosDropBitsOutPerSecond` |BitsPerSecond |Average |\<none\>|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|