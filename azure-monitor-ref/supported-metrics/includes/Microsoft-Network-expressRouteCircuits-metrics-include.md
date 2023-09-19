---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Network/expressRouteCircuits, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Arp Availability<p><p>ARP Availability from MSEE towards all peers. |`ArpAvailability` |Percent |Average |PeeringType, Peer|PT1M |Yes|
|Bgp Availability<p><p>BGP Availability from MSEE towards all peers. |`BgpAvailability` |Percent |Average |PeeringType, Peer|PT1M |Yes|
|BitsInPerSecond<p><p>Bits ingressing Azure per second |`BitsInPerSecond` |BitsPerSecond |Average |PeeringType, DeviceRole|PT1M |Yes|
|BitsOutPerSecond<p><p>Bits egressing Azure per second |`BitsOutPerSecond` |BitsPerSecond |Average |PeeringType, DeviceRole|PT1M |Yes|
|FastPathRoutesCount<p><p>Count of fastpath routes configured on circuit |`FastPathRoutesCountForCircuit` |Count |Maximum |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|GlobalReachBitsInPerSecond<p><p>Bits ingressing Azure per second |`GlobalReachBitsInPerSecond` |BitsPerSecond |Average |PeeredCircuitSKey|PT1M |No|
|GlobalReachBitsOutPerSecond<p><p>Bits egressing Azure per second |`GlobalReachBitsOutPerSecond` |BitsPerSecond |Average |PeeredCircuitSKey|PT1M |No|
|DroppedInBitsPerSecond<p><p>Ingress bits of data dropped per second |`QosDropBitsInPerSecond` |BitsPerSecond |Average |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|DroppedOutBitsPerSecond<p><p>Egress bits of data dropped per second |`QosDropBitsOutPerSecond` |BitsPerSecond |Average |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|