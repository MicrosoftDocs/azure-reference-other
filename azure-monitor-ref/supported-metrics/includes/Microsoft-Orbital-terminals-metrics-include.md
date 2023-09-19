---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Orbital/terminals, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|SDWAN alarms<p><p>SDWAN alarms |`JuniperAlarm` |Count |Total, Count |category, id, message, node, number, process, router, severity, shelvedReason, source, time|PT1M |Yes|
|Satcom SDWAN bandwidth<p><p>Satcom SDWAN bandwidth in bytes per second |`JuniperSsrBandwidthBytesPerSecond` |BytesPerSecond |Average |No Dimensions|PT1M |Yes|
|Satcom SDWAN bytes<p><p>Satcom SDWAN total bytes |`JuniperSsrBytes` |Bytes |Average |No Dimensions|PT1M |Yes|
|Satcom SDWAN packet loss<p><p>Satcom SDWAN total packets lost |`JuniperSsrPacketLoss` |Count |Average |No Dimensions|PT1M |Yes|