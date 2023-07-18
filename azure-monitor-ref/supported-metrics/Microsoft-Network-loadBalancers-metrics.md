---
title: Supported metrics - Microsoft.Network/loadBalancers
description: Reference for Microsoft.Network/loadBalancers metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Network/loadBalancers  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Network/loadBalancers resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Allocated SNAT Ports<p><p>Total number of SNAT ports allocated within time period |`AllocatedSnatPorts` |Count |Average |FrontendIPAddress, BackendIPAddress, ProtocolType, IsAwaitingRemoval |No|
|Byte Count<p><p>Total number of Bytes transmitted within time period |`ByteCount` |Bytes |Total |FrontendIPAddress, FrontendPort, Direction |Yes|
|Health Probe Status<p><p>Average Load Balancer health probe status per time duration |`DipAvailability` |Count |Average |ProtocolType, BackendPort, FrontendIPAddress, FrontendPort, BackendIPAddress |Yes|
|Health Probe Status<p><p>Azure Cross-region Load Balancer backend health and status per time duration |`GlobalBackendAvailability` |Count |Average |FrontendIPAddress, FrontendPort, BackendIPAddress, ProtocolType, FrontendRegion, BackendRegion |Yes|
|Packet Count<p><p>Total number of Packets transmitted within time period |`PacketCount` |Count |Total |FrontendIPAddress, FrontendPort, Direction |Yes|
|SNAT Connection Count<p><p>Total number of new SNAT connections created within time period |`SnatConnectionCount` |Count |Total |FrontendIPAddress, BackendIPAddress, ConnectionState |Yes|
|SYN Count<p><p>Total number of SYN Packets transmitted within time period |`SYNCount` |Count |Total |FrontendIPAddress, FrontendPort, Direction |Yes|
|Used SNAT Ports<p><p>Total number of SNAT ports used within time period |`UsedSnatPorts` |Count |Average |FrontendIPAddress, BackendIPAddress, ProtocolType, IsAwaitingRemoval |No|
|Data Path Availability<p><p>Average Load Balancer data path availability per time duration |`VipAvailability` |Count |Average |FrontendIPAddress, FrontendPort |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->