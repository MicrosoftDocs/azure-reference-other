---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Network/natGateways, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Bytes**<br><br>Total number of Bytes transmitted within time period |`ByteCount` |Bytes |Total |`Protocol`, `Direction`|PT1M, PT1H |No|
|**Datapath Availability (Preview)**<br><br>NAT Gateway Datapath Availability |`DatapathAvailability` |Count |Average |\<none\>|PT1M, PT1H |No|
|**Packets**<br><br>Total number of Packets transmitted within time period |`PacketCount` |Count |Total |`Protocol`, `Direction`|PT1M, PT1H |No|
|**Dropped Packets**<br><br>Count of dropped packets |`PacketDropCount` |Count |Total |\<none\>|PT1M, PT1H |No|
|**SNAT Connection Count**<br><br>Total concurrent active connections |`SNATConnectionCount` |Count |Total |`Protocol`, `ConnectionState`|PT1M, PT1H |No|
|**Total SNAT Connection Count**<br><br>Total number of active SNAT connections |`TotalConnectionCount` |Count |Total |`Protocol`|PT1M, PT1H |No|