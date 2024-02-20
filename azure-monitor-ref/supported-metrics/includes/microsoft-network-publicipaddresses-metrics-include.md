---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Network/publicIPAddresses, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Byte Count**<br><br>Total number of Bytes transmitted within time period |`ByteCount` |Bytes |Total |`Port`, `Direction`|PT1M |Yes|
|**Inbound bytes dropped DDoS**<br><br>Inbound bytes dropped DDoS |`BytesDroppedDDoS` |BytesPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Inbound bytes forwarded DDoS**<br><br>Inbound bytes forwarded DDoS |`BytesForwardedDDoS` |BytesPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Inbound bytes DDoS**<br><br>Inbound bytes DDoS |`BytesInDDoS` |BytesPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Inbound SYN packets to trigger DDoS mitigation**<br><br>Inbound SYN packets to trigger DDoS mitigation |`DDoSTriggerSYNPackets` |CountPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Inbound TCP packets to trigger DDoS mitigation**<br><br>Inbound TCP packets to trigger DDoS mitigation |`DDoSTriggerTCPPackets` |CountPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Inbound UDP packets to trigger DDoS mitigation**<br><br>Inbound UDP packets to trigger DDoS mitigation |`DDoSTriggerUDPPackets` |CountPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Under DDoS attack or not**<br><br>Under DDoS attack or not |`IfUnderDDoSAttack` |Count |Maximum |\<none\>|PT1M |Yes|
|**Packet Count**<br><br>Total number of Packets transmitted within time period |`PacketCount` |Count |Total |`Port`, `Direction`|PT1M |Yes|
|**Inbound packets dropped DDoS**<br><br>Inbound packets dropped DDoS |`PacketsDroppedDDoS` |CountPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Inbound packets forwarded DDoS**<br><br>Inbound packets forwarded DDoS |`PacketsForwardedDDoS` |CountPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Inbound packets DDoS**<br><br>Inbound packets DDoS |`PacketsInDDoS` |CountPerSecond |Maximum |\<none\>|PT1M |Yes|
|**SYN Count**<br><br>Total number of SYN Packets transmitted within time period |`SynCount` |Count |Total |`Port`, `Direction`|PT1M |Yes|
|**Inbound TCP bytes dropped DDoS**<br><br>Inbound TCP bytes dropped DDoS |`TCPBytesDroppedDDoS` |BytesPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Inbound TCP bytes forwarded DDoS**<br><br>Inbound TCP bytes forwarded DDoS |`TCPBytesForwardedDDoS` |BytesPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Inbound TCP bytes DDoS**<br><br>Inbound TCP bytes DDoS |`TCPBytesInDDoS` |BytesPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Inbound TCP packets dropped DDoS**<br><br>Inbound TCP packets dropped DDoS |`TCPPacketsDroppedDDoS` |CountPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Inbound TCP packets forwarded DDoS**<br><br>Inbound TCP packets forwarded DDoS |`TCPPacketsForwardedDDoS` |CountPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Inbound TCP packets DDoS**<br><br>Inbound TCP packets DDoS |`TCPPacketsInDDoS` |CountPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Inbound UDP bytes dropped DDoS**<br><br>Inbound UDP bytes dropped DDoS |`UDPBytesDroppedDDoS` |BytesPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Inbound UDP bytes forwarded DDoS**<br><br>Inbound UDP bytes forwarded DDoS |`UDPBytesForwardedDDoS` |BytesPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Inbound UDP bytes DDoS**<br><br>Inbound UDP bytes DDoS |`UDPBytesInDDoS` |BytesPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Inbound UDP packets dropped DDoS**<br><br>Inbound UDP packets dropped DDoS |`UDPPacketsDroppedDDoS` |CountPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Inbound UDP packets forwarded DDoS**<br><br>Inbound UDP packets forwarded DDoS |`UDPPacketsForwardedDDoS` |CountPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Inbound UDP packets DDoS**<br><br>Inbound UDP packets DDoS |`UDPPacketsInDDoS` |CountPerSecond |Maximum |\<none\>|PT1M |Yes|
|**Data Path Availability**<br><br>Average IP Address availability per time duration |`VipAvailability` |Count |Average |`Port`|PT1M |Yes|