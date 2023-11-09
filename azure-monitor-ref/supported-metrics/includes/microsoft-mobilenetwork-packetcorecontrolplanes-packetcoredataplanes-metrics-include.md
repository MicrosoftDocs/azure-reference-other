---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.MobileNetwork/packetcorecontrolplanes/packetcoredataplanes, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Data Plane Bandwidth**<p><p>Data plane bandwidth for all traffic types (bits/second). |`DataPlaneBandwidth` |BitsPerSecond |Total |`SiteId`, `Direction`, `Interface`|PT1M |No|
|**Data Plane Packet Drop Rate**<p><p>Data plane packet drop rate for all traffic types (packets/sec). |`DataPlanePacketDropRate` |CountPerSecond |Total |`SiteId`, `Cause`, `Direction`, `Interface`|PT1M |No|
|**Data Plane Packet Rate**<p><p>Data plane packet rate for all traffic types (packets/sec). |`DataPlanePacketRate` |CountPerSecond |Total |`SiteId`, `Direction`, `Interface`|PT1M |No|
|**N3 Bandwidth**<p><p>N3 bandwidth for all traffic types (bits/second). |`N3Bandwidth` |BitsPerSecond |Total |`SiteId`, `Direction`, `RanId`|PT1M |No|
|**N3 Packet Rate**<p><p>N3 packet rate for all traffic types (packets/sec). |`N3PacketRate` |CountPerSecond |Total |`SiteId`, `Direction`|PT1M |No|
|**N6 Bandwidth**<p><p>N6 bandwidth for all traffic types (bits/second). |`N6Bandwidth` |BitsPerSecond |Total |`SiteId`, `Direction`, `Dnn`|PT1M |No|
|**N6 Packet Rate**<p><p>N6 packet rate for all traffic types (packets/sec). |`N6PacketRate` |CountPerSecond |Total |`SiteId`, `Direction`, `Dnn`|PT1M |No|