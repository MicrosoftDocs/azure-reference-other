---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/07/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.MobileNetwork/packetcorecontrolplanes/packetcoredataplanes, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Traffic|**Data Plane Bandwidth**<p><p>Data plane bandwidth for all traffic types (bits/second). |`DataPlaneBandwidth` |BitsPerSecond |Total |`SiteId`, `Direction`, `Interface`|PT1M |No|
|Traffic|**Data Plane Packet Drop Rate**<p><p>Data plane packet drop rate for all traffic types (packets/sec). |`DataPlanePacketDropRate` |CountPerSecond |Total |`SiteId`, `Cause`, `Direction`, `Interface`|PT1M |No|
|Traffic|**Data Plane Packet Rate**<p><p>Data plane packet rate for all traffic types (packets/sec). |`DataPlanePacketRate` |CountPerSecond |Total |`SiteId`, `Direction`, `Interface`, `Result`|PT1M |No|
|Traffic|**ICMP Pinhole Packet Count**<p><p>The number of ICMP packets that have created a pinhole, been forwarded upstream or forwarded downstream. |`ICMPPinholePacketCount` |Count |Total |`SiteId`, `type`, `Dnn`|PT1M |No|
|Traffic|**N3 Bandwidth**<p><p>N3 bandwidth for all traffic types (bits/second) per RanId. |`N3Bandwidth` |BitsPerSecond |Total |`SiteId`, `Direction`, `RanId`|PT1M |No|
|Traffic|**N3 Packet Rate**<p><p>N3 packet rate for all traffic types (packets/sec). |`N3PacketRate` |CountPerSecond |Total |`SiteId`, `Direction`|PT1M |No|
|Traffic|**N6 Bandwidth**<p><p>N6 bandwidth for all traffic types (bits/second). |`N6Bandwidth` |BitsPerSecond |Total |`SiteId`, `Direction`, `Dnn`|PT1M |No|
|Traffic|**N6 Packet Rate**<p><p>N6 packet rate for all traffic types (packets/sec). |`N6PacketRate` |CountPerSecond |Total |`SiteId`, `Direction`, `Dnn`|PT1M |No|
|Traffic|**Pinholes protocol limit exceeded**<p><p>The number of pinholes rejected due to the per-interface per-protocol limit.  |`PinholeProtocolLimitExceeded` |Count |Total |`SiteId`, `Type`|PT1M |No|
|Traffic|**Pinholes Active**<p><p>The current number of dynamic match actions created. TCP and UDP pinholes consist of 3 dynamic match actions, ICMP echo pinholes consist of 2 |`PinholesActive` |Count |Total |`SiteId`, `Type`, `Interface`|PT1M |No|
|Traffic|**Pinhole Creation Rate**<p><p>The total number of dynamic match actions created. TCP and UDP pinholes consist of 3 dynamic match actions, ICMP echo pinholes consist of 2.  |`PinholesCreationRate` |Count |Total |`SiteId`, `Type`, `Interface`|PT1M |No|
|Traffic|**Pinholes failures**<p><p>The number of times learning has failed for each learn action. |`PinholesFailures` |Count |Total |`SiteId`, `Type`, `Interface`|PT1M |No|
|Traffic|**Pinholes Timeout Rate**<p><p>The number of dynamic match actions that have timed out due to inactivity. TCP and UDP pinholes consist of 3 dynamic match actions, ICMP echo pinholes consist of 2.  |`PinholesTimeoutRate` |Count |Total |`SiteId`, `Type`, `Interface`|PT1M |No|
|Traffic|**Pinhole UE limit exceeded**<p><p>The number of pinholes rejected due to the per-source IP address limit.  |`PinholesUELimitExceeded` |Count |Total |`SiteId`, `Type`|PT1M |No|
|Traffic|**Tcp Pinhole Packet Count**<p><p>The number of TCP packets that have created a pinhole, been forwarded upstream or forwarded downstream. |`TcpPinholePacketCount` |Count |Total |`SiteId`, `type`, `Dnn`|PT1M |No|
|Traffic|**Total N3 Bandwidth**<p><p>Total N3 bandwidth for all traffic types (bits/second) per interface. |`TotalN3Bandwidth` |BitsPerSecond |Total |`SiteId`, `Direction`|PT1M |No|
|Traffic|**UDP Pinhole Packet Count**<p><p>The number of UDP packets that have created a pinhole, been forwarded upstream or forwarded downstream. |`UdpPinholePacketCount` |Count |Total |`SiteId`, `type`, `Dnn`|PT1M |No|