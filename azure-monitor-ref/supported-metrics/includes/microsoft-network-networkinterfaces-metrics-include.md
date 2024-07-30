---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.Network/networkinterfaces, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Bytes Received**<br><br>Number of bytes the Network Interface received |`BytesReceivedRate` |Bytes |Total |\<none\>|PT1M |Yes|
|**Bytes Sent**<br><br>Number of bytes the Network Interface sent |`BytesSentRate` |Bytes |Total |\<none\>|PT1M |Yes|
|**Inbound Flows Maximum Creation Rate**<br><br>The maximum creation rate of inbound flows (traffic going into the NIC) |`CreationRateMaxTotalFlowsIn` |CountPerSecond |Average |\<none\>|PT1M |No|
|**Outbound Flows Maximum Creation Rate**<br><br>The maximum creation rate of outbound flows (traffic going out of the NIC) |`CreationRateMaxTotalFlowsOut` |CountPerSecond |Average |\<none\>|PT1M |No|
|**Inbound Flows**<br><br>Inbound Flows are number of current flows in the inbound direction (traffic going into the NIC) |`CurrentTotalFlowsIn` |Count |Average |\<none\>|PT1M |No|
|**Outbound Flows**<br><br>Outbound Flows are number of current flows in the outbound direction (traffic going out of the NIC) |`CurrentTotalFlowsOut` |Count |Average |\<none\>|PT1M |No|
|**Packets Received**<br><br>Number of packets the Network Interface received |`PacketsReceivedRate` |Count |Total |\<none\>|PT1M |Yes|
|**Packets Sent**<br><br>Number of packets the Network Interface sent |`PacketsSentRate` |Count |Total |\<none\>|PT1M |Yes|