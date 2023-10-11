---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/02/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.MobileNetwork/packetcorecontrolplanes/packetcoredataplanes, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Data Plane Bandwidth<p><p>Data plane bandwidth for all traffic types (bits/second). |`DataPlaneBandwidth` |BitsPerSecond |Total |SiteId, Direction, Interface|PT1M |No|
|Data Plane Packet Drop Rate<p><p>Data plane packet drop rate for all traffic types (packets/sec). |`DataPlanePacketDropRate` |CountPerSecond |Total |SiteId, Cause, Direction, Interface|PT1M |No|
|Data Plane Packet Rate<p><p>Data plane packet rate for all traffic types (packets/sec). |`DataPlanePacketRate` |CountPerSecond |Total |SiteId, Direction, Interface|PT1M |No|