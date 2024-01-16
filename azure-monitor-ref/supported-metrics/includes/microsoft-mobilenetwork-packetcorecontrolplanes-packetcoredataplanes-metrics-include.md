---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.MobileNetwork/packetcorecontrolplanes/packetcoredataplanes, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Traffic|**Data Plane Bandwidth**<p><p>Data plane bandwidth for all traffic types (bits/second). |`DataPlaneBandwidth` |BitsPerSecond |Total |`SiteId`, `Direction`, `Interface`|PT1M |No|
|Traffic|**Data Plane Packet Drop Rate**<p><p>Data plane packet drop rate for all traffic types (packets/sec). |`DataPlanePacketDropRate` |CountPerSecond |Total |`SiteId`, `Cause`, `Direction`, `Interface`|PT1M |No|
|Traffic|**Data Plane Packet Rate**<p><p>Data plane packet rate for all traffic types (packets/sec). |`DataPlanePacketRate` |CountPerSecond |Total |`SiteId`, `Direction`, `Interface`|PT1M |No|
|Traffic|**N3 Bandwidth**<p><p>N3 bandwidth for all traffic types (bits/second). |`N3Bandwidth` |BitsPerSecond |Total |`SiteId`, `Direction`, `RanId`|PT1M |No|
|Traffic|**N3 Packet Rate**<p><p>N3 packet rate for all traffic types (packets/sec). |`N3PacketRate` |CountPerSecond |Total |`SiteId`, `Direction`|PT1M |No|
|Traffic|**N6 Bandwidth**<p><p>N6 bandwidth for all traffic types (bits/second). |`N6Bandwidth` |BitsPerSecond |Total |`SiteId`, `Direction`, `Dnn`|PT1M |No|
|Traffic|**N6 Packet Rate**<p><p>N6 packet rate for all traffic types (packets/sec). |`N6PacketRate` |CountPerSecond |Total |`SiteId`, `Direction`, `Dnn`|PT1M |No|