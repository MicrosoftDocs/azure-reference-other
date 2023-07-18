---
title: Supported metrics - Microsoft.Network/publicIPAddresses
description: Reference for Microsoft.Network/publicIPAddresses metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Network/publicIPAddresses  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Network/publicIPAddresses resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Byte Count<p><p>Total number of Bytes transmitted within time period |`ByteCount` |Bytes |Total |Port, Direction |Yes|
|Inbound bytes dropped DDoS<p><p>Inbound bytes dropped DDoS |`BytesDroppedDDoS` |BytesPerSecond |Maximum |No Dimensions |Yes|
|Inbound bytes forwarded DDoS<p><p>Inbound bytes forwarded DDoS |`BytesForwardedDDoS` |BytesPerSecond |Maximum |No Dimensions |Yes|
|Inbound bytes DDoS<p><p>Inbound bytes DDoS |`BytesInDDoS` |BytesPerSecond |Maximum |No Dimensions |Yes|
|Inbound SYN packets to trigger DDoS mitigation<p><p>Inbound SYN packets to trigger DDoS mitigation |`DDoSTriggerSYNPackets` |CountPerSecond |Maximum |No Dimensions |Yes|
|Inbound TCP packets to trigger DDoS mitigation<p><p>Inbound TCP packets to trigger DDoS mitigation |`DDoSTriggerTCPPackets` |CountPerSecond |Maximum |No Dimensions |Yes|
|Inbound UDP packets to trigger DDoS mitigation<p><p>Inbound UDP packets to trigger DDoS mitigation |`DDoSTriggerUDPPackets` |CountPerSecond |Maximum |No Dimensions |Yes|
|Under DDoS attack or not<p><p>Under DDoS attack or not |`IfUnderDDoSAttack` |Count |Maximum |No Dimensions |Yes|
|Packet Count<p><p>Total number of Packets transmitted within time period |`PacketCount` |Count |Total |Port, Direction |Yes|
|Inbound packets dropped DDoS<p><p>Inbound packets dropped DDoS |`PacketsDroppedDDoS` |CountPerSecond |Maximum |No Dimensions |Yes|
|Inbound packets forwarded DDoS<p><p>Inbound packets forwarded DDoS |`PacketsForwardedDDoS` |CountPerSecond |Maximum |No Dimensions |Yes|
|Inbound packets DDoS<p><p>Inbound packets DDoS |`PacketsInDDoS` |CountPerSecond |Maximum |No Dimensions |Yes|
|SYN Count<p><p>Total number of SYN Packets transmitted within time period |`SynCount` |Count |Total |Port, Direction |Yes|
|Inbound TCP bytes dropped DDoS<p><p>Inbound TCP bytes dropped DDoS |`TCPBytesDroppedDDoS` |BytesPerSecond |Maximum |No Dimensions |Yes|
|Inbound TCP bytes forwarded DDoS<p><p>Inbound TCP bytes forwarded DDoS |`TCPBytesForwardedDDoS` |BytesPerSecond |Maximum |No Dimensions |Yes|
|Inbound TCP bytes DDoS<p><p>Inbound TCP bytes DDoS |`TCPBytesInDDoS` |BytesPerSecond |Maximum |No Dimensions |Yes|
|Inbound TCP packets dropped DDoS<p><p>Inbound TCP packets dropped DDoS |`TCPPacketsDroppedDDoS` |CountPerSecond |Maximum |No Dimensions |Yes|
|Inbound TCP packets forwarded DDoS<p><p>Inbound TCP packets forwarded DDoS |`TCPPacketsForwardedDDoS` |CountPerSecond |Maximum |No Dimensions |Yes|
|Inbound TCP packets DDoS<p><p>Inbound TCP packets DDoS |`TCPPacketsInDDoS` |CountPerSecond |Maximum |No Dimensions |Yes|
|Inbound UDP bytes dropped DDoS<p><p>Inbound UDP bytes dropped DDoS |`UDPBytesDroppedDDoS` |BytesPerSecond |Maximum |No Dimensions |Yes|
|Inbound UDP bytes forwarded DDoS<p><p>Inbound UDP bytes forwarded DDoS |`UDPBytesForwardedDDoS` |BytesPerSecond |Maximum |No Dimensions |Yes|
|Inbound UDP bytes DDoS<p><p>Inbound UDP bytes DDoS |`UDPBytesInDDoS` |BytesPerSecond |Maximum |No Dimensions |Yes|
|Inbound UDP packets dropped DDoS<p><p>Inbound UDP packets dropped DDoS |`UDPPacketsDroppedDDoS` |CountPerSecond |Maximum |No Dimensions |Yes|
|Inbound UDP packets forwarded DDoS<p><p>Inbound UDP packets forwarded DDoS |`UDPPacketsForwardedDDoS` |CountPerSecond |Maximum |No Dimensions |Yes|
|Inbound UDP packets DDoS<p><p>Inbound UDP packets DDoS |`UDPPacketsInDDoS` |CountPerSecond |Maximum |No Dimensions |Yes|
|Data Path Availability<p><p>Average IP Address availability per time duration |`VipAvailability` |Count |Average |Port |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->