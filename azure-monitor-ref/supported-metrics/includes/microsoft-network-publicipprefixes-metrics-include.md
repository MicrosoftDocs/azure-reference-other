---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Network/publicIPPrefixes, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Inbound bytes dropped DDoS**<br><br>Inbound bytes dropped DDoS |`BytesDroppedDDoS` |BytesPerSecond |Maximum |`DestinationVIP`|PT1M |Yes|
|**Inbound bytes forwarded DDoS**<br><br>Inbound bytes forwarded DDoS |`BytesForwardedDDoS` |BytesPerSecond |Maximum |`DestinationVIP`|PT1M |Yes|
|**Inbound bytes DDoS**<br><br>Inbound bytes DDoS |`BytesInDDoS` |BytesPerSecond |Maximum |`DestinationVIP`|PT1M |Yes|
|**Inbound SYN packets to trigger DDoS mitigation**<br><br>Inbound SYN packets to trigger DDoS mitigation |`DDoSTriggerSYNPackets` |CountPerSecond |Maximum |`VipAddress`|PT1M |Yes|
|**Inbound TCP packets to trigger DDoS mitigation**<br><br>Inbound TCP packets to trigger DDoS mitigation |`DDoSTriggerTCPPackets` |CountPerSecond |Maximum |`VipAddress`|PT1M |Yes|
|**Inbound UDP packets to trigger DDoS mitigation**<br><br>Inbound UDP packets to trigger DDoS mitigation |`DDoSTriggerUDPPackets` |CountPerSecond |Maximum |`VipAddress`|PT1M |Yes|
|**Under DDoS attack or not**<br><br>Under DDoS attack or not |`IfUnderDDoSAttack` |Count |Maximum |`DestinationVIP`|PT1M |Yes|
|**Inbound packets dropped DDoS**<br><br>Inbound packets dropped DDoS |`PacketsDroppedDDoS` |CountPerSecond |Maximum |`DestinationVIP`|PT1M |Yes|
|**Inbound packets forwarded DDoS**<br><br>Inbound packets forwarded DDoS |`PacketsForwardedDDoS` |CountPerSecond |Maximum |`DestinationVIP`|PT1M |Yes|
|**Inbound packets DDoS**<br><br>Inbound packets DDoS |`PacketsInDDoS` |CountPerSecond |Maximum |`DestinationVIP`|PT1M |Yes|
|**Inbound TCP bytes dropped DDoS**<br><br>Inbound TCP bytes dropped DDoS |`TCPBytesDroppedDDoS` |BytesPerSecond |Maximum |`DestinationVIP`|PT1M |Yes|
|**Inbound TCP bytes forwarded DDoS**<br><br>Inbound TCP bytes forwarded DDoS |`TCPBytesForwardedDDoS` |BytesPerSecond |Maximum |`DestinationVIP`|PT1M |Yes|
|**Inbound TCP bytes DDoS**<br><br>Inbound TCP bytes DDoS |`TCPBytesInDDoS` |BytesPerSecond |Maximum |`DestinationVIP`|PT1M |Yes|
|**Inbound TCP packets dropped DDoS**<br><br>Inbound TCP packets dropped DDoS |`TCPPacketsDroppedDDoS` |CountPerSecond |Maximum |`DestinationVIP`|PT1M |Yes|
|**Inbound TCP packets forwarded DDoS**<br><br>Inbound TCP packets forwarded DDoS |`TCPPacketsForwardedDDoS` |CountPerSecond |Maximum |`DestinationVIP`|PT1M |Yes|
|**Inbound TCP packets DDoS**<br><br>Inbound TCP packets DDoS |`TCPPacketsInDDoS` |CountPerSecond |Maximum |`DestinationVIP`|PT1M |Yes|
|**Inbound UDP bytes dropped DDoS**<br><br>Inbound UDP bytes dropped DDoS |`UDPBytesDroppedDDoS` |BytesPerSecond |Maximum |`DestinationVIP`|PT1M |Yes|
|**Inbound UDP bytes forwarded DDoS**<br><br>Inbound UDP bytes forwarded DDoS |`UDPBytesForwardedDDoS` |BytesPerSecond |Maximum |`DestinationVIP`|PT1M |Yes|
|**Inbound UDP bytes DDoS**<br><br>Inbound UDP bytes DDoS |`UDPBytesInDDoS` |BytesPerSecond |Maximum |`DestinationVIP`|PT1M |Yes|
|**Inbound UDP packets dropped DDoS**<br><br>Inbound UDP packets dropped DDoS |`UDPPacketsDroppedDDoS` |CountPerSecond |Maximum |`DestinationVIP`|PT1M |Yes|
|**Inbound UDP packets forwarded DDoS**<br><br>Inbound UDP packets forwarded DDoS |`UDPPacketsForwardedDDoS` |CountPerSecond |Maximum |`DestinationVIP`|PT1M |Yes|
|**Inbound UDP packets DDoS**<br><br>Inbound UDP packets DDoS |`UDPPacketsInDDoS` |CountPerSecond |Maximum |`DestinationVIP`|PT1M |Yes|