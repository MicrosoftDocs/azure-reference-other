---
title: Supported metrics - Microsoft.Network/expressRouteCircuits
description: Reference for Microsoft.Network/expressRouteCircuits metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Network/expressRouteCircuits  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Network/expressRouteCircuits resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Arp Availability<p><p>ARP Availability from MSEE towards all peers. |`ArpAvailability` |Percent |Average |PeeringType, Peer |Yes|
|Bgp Availability<p><p>BGP Availability from MSEE towards all peers. |`BgpAvailability` |Percent |Average |PeeringType, Peer |Yes|
|BitsInPerSecond<p><p>Bits ingressing Azure per second |`BitsInPerSecond` |BitsPerSecond |Average |PeeringType, DeviceRole |Yes|
|BitsOutPerSecond<p><p>Bits egressing Azure per second |`BitsOutPerSecond` |BitsPerSecond |Average |PeeringType, DeviceRole |Yes|
|FastPathRoutesCount<p><p>Count of fastpath routes configured on circuit |`FastPathRoutesCountForCircuit` |Count |Maximum |No Dimensions |Yes|
|GlobalReachBitsInPerSecond<p><p>Bits ingressing Azure per second |`GlobalReachBitsInPerSecond` |BitsPerSecond |Average |PeeredCircuitSKey |No|
|GlobalReachBitsOutPerSecond<p><p>Bits egressing Azure per second |`GlobalReachBitsOutPerSecond` |BitsPerSecond |Average |PeeredCircuitSKey |No|
|DroppedInBitsPerSecond<p><p>Ingress bits of data dropped per second |`QosDropBitsInPerSecond` |BitsPerSecond |Average |No Dimensions |Yes|
|DroppedOutBitsPerSecond<p><p>Egress bits of data dropped per second |`QosDropBitsOutPerSecond` |BitsPerSecond |Average |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->