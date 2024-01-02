---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Network/networkInterfaces, arm
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Bytes Received**<p><p>Number of bytes the Network Interface received |`BytesReceivedRate` |Bytes |Total |\<none\>|PT1M, PT1H |Yes|
|**Bytes Sent**<p><p>Number of bytes the Network Interface sent |`BytesSentRate` |Bytes |Total |\<none\>|PT1M, PT1H |Yes|
|**Packets Received**<p><p>Number of packets the Network Interface received |`PacketsReceivedRate` |Count |Total |\<none\>|PT1M, PT1H |Yes|
|**Packets Sent**<p><p>Number of packets the Network Interface sent |`PacketsSentRate` |Count |Total |\<none\>|PT1M, PT1H |Yes|