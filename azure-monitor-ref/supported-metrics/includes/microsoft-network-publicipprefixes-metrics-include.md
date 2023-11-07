---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Network/publicIPPrefixes, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Inbound bytes dropped DDoS**<p><p>Inbound bytes dropped DDoS |`BytesDroppedDDoS` |BytesPerSecond |Maximum |`DestinationVIP`|PT1M |Yes|
|**Inbound bytes forwarded DDoS**<p><p>Inbound bytes forwarded DDoS |`BytesForwardedDDoS` |BytesPerSecond |Maximum |`DestinationVIP`|PT1M |Yes|
|**Inbound bytes DDoS**<p><p>Inbound bytes DDoS |`BytesInDDoS` |BytesPerSecond |Maximum |`DestinationVIP`|PT1M |Yes|
|**Inbound SYN packets to trigger DDoS mitigation**<p><p>Inbound SYN packets to trigger DDoS mitigation |`DDoSTriggerSYNPackets` |CountPerSecond |Maximum |`VipAddress`|PT1M |Yes|
|**Inbound TCP packets to trigger DDoS mitigation**<p><p>Inbound TCP packets to trigger DDoS mitigation |`DDoSTriggerTCPPackets` |CountPerSecond |Maximum |`VipAddress`|PT1M |Yes|
|**Inbound UDP packets to trigger DDoS mitigation**<p><p>Inbound UDP packets to trigger DDoS mitigation |`DDoSTriggerUDPPackets` |CountPerSecond |Maximum |`VipAddress`|PT1M |Yes|
|**Under DDoS attack or not**<p><p>Under DDoS attack or not |`IfUnderDDoSAttack` |Count |Maximum |`DestinationVIP`|PT1M |Yes|
|**Inbound packets dropped DDoS**<p><p>Inbound packets dropped DDoS |`PacketsDroppedDDoS` |CountPerSecond |Maximum |`DestinationVIP`|PT1M |Yes|
|**Inbound packets forwarded DDoS**<p><p>Inbound packets forwarded DDoS |`PacketsForwardedDDoS` |CountPerSecond |Maximum |`DestinationVIP`|PT1M |Yes|
|**Inbound packets DDoS**<p><p>Inbound packets DDoS |`PacketsInDDoS` |CountPerSecond |Maximum |`DestinationVIP`|PT1M |Yes|
|**Inbound TCP bytes dropped DDoS**<p><p>Inbound TCP bytes dropped DDoS |`TCPBytesDroppedDDoS` |BytesPerSecond |Maximum |`DestinationVIP`|PT1M |Yes|
|**Inbound TCP bytes forwarded DDoS**<p><p>Inbound TCP bytes forwarded DDoS |`TCPBytesForwardedDDoS` |BytesPerSecond |Maximum |`DestinationVIP`|PT1M |Yes|
|**Inbound TCP bytes DDoS**<p><p>Inbound TCP bytes DDoS |`TCPBytesInDDoS` |BytesPerSecond |Maximum |`DestinationVIP`|PT1M |Yes|
|**Inbound TCP packets dropped DDoS**<p><p>Inbound TCP packets dropped DDoS |`TCPPacketsDroppedDDoS` |CountPerSecond |Maximum |`DestinationVIP`|PT1M |Yes|
|**Inbound TCP packets forwarded DDoS**<p><p>Inbound TCP packets forwarded DDoS |`TCPPacketsForwardedDDoS` |CountPerSecond |Maximum |`DestinationVIP`|PT1M |Yes|
|**Inbound TCP packets DDoS**<p><p>Inbound TCP packets DDoS |`TCPPacketsInDDoS` |CountPerSecond |Maximum |`DestinationVIP`|PT1M |Yes|
|**Inbound UDP bytes dropped DDoS**<p><p>Inbound UDP bytes dropped DDoS |`UDPBytesDroppedDDoS` |BytesPerSecond |Maximum |`DestinationVIP`|PT1M |Yes|
|**Inbound UDP bytes forwarded DDoS**<p><p>Inbound UDP bytes forwarded DDoS |`UDPBytesForwardedDDoS` |BytesPerSecond |Maximum |`DestinationVIP`|PT1M |Yes|
|**Inbound UDP bytes DDoS**<p><p>Inbound UDP bytes DDoS |`UDPBytesInDDoS` |BytesPerSecond |Maximum |`DestinationVIP`|PT1M |Yes|
|**Inbound UDP packets dropped DDoS**<p><p>Inbound UDP packets dropped DDoS |`UDPPacketsDroppedDDoS` |CountPerSecond |Maximum |`DestinationVIP`|PT1M |Yes|
|**Inbound UDP packets forwarded DDoS**<p><p>Inbound UDP packets forwarded DDoS |`UDPPacketsForwardedDDoS` |CountPerSecond |Maximum |`DestinationVIP`|PT1M |Yes|
|**Inbound UDP packets DDoS**<p><p>Inbound UDP packets DDoS |`UDPPacketsInDDoS` |CountPerSecond |Maximum |`DestinationVIP`|PT1M |Yes|