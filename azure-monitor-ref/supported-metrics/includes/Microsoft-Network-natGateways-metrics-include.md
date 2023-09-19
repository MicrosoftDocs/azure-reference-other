---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Network/natGateways, arm
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Bytes<p><p>Total number of Bytes transmitted within time period |`ByteCount` |Bytes |Total |Protocol, Direction|PT1M, PT1H |No|
|Datapath Availability (Preview)<p><p>NAT Gateway Datapath Availability |`DatapathAvailability` |Count |Average |No Dimensions|PT1M, PT1H |No|
|Packets<p><p>Total number of Packets transmitted within time period |`PacketCount` |Count |Total |Protocol, Direction|PT1M, PT1H |No|
|Dropped Packets<p><p>Count of dropped packets |`PacketDropCount` |Count |Total |No Dimensions|PT1M, PT1H |No|
|SNAT Connection Count<p><p>Total concurrent active connections |`SNATConnectionCount` |Count |Total |Protocol, ConnectionState|PT1M, PT1H |No|
|Total SNAT Connection Count<p><p>Total number of active SNAT connections |`TotalConnectionCount` |Count |Total |Protocol|PT1M, PT1H |No|