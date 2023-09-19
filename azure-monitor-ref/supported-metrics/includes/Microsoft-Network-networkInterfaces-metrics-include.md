---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Network/networkInterfaces, arm
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Bytes Received<p><p>Number of bytes the Network Interface received |`BytesReceivedRate` |Bytes |Total |No Dimensions|PT1M, PT1H |Yes|
|Bytes Sent<p><p>Number of bytes the Network Interface sent |`BytesSentRate` |Bytes |Total |No Dimensions|PT1M, PT1H |Yes|
|Packets Received<p><p>Number of packets the Network Interface received |`PacketsReceivedRate` |Count |Total |No Dimensions|PT1M, PT1H |Yes|
|Packets Sent<p><p>Number of packets the Network Interface sent |`PacketsSentRate` |Count |Total |No Dimensions|PT1M, PT1H |Yes|