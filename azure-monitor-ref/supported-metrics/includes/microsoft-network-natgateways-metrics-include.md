---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.Network/natgateways, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Bytes**<br><br>Total number of Bytes transmitted within time period |`ByteCount` |Bytes |Total |`Protocol`, `Direction`|PT1M |Yes|
|**Datapath Availability (Preview)**<br><br>NAT Gateway Datapath Availability |`DatapathAvailability` |Count |Average |\<none\>|PT1M |Yes|
|**Packets**<br><br>Total number of Packets transmitted within time period |`PacketCount` |Count |Total |`Protocol`, `Direction`|PT1M |Yes|
|**Dropped Packets**<br><br>Count of dropped packets |`PacketDropCount` |Count |Total |\<none\>|PT1M |Yes|
|**SNAT Connection Count**<br><br>Total concurrent active connections |`SNATConnectionCount` |Count |Total |`Protocol`, `ConnectionState`|PT1M |Yes|
|**Total SNAT Connection Count**<br><br>Total number of active SNAT connections |`TotalConnectionCount` |Count |Total |`Protocol`|PT1M |Yes|