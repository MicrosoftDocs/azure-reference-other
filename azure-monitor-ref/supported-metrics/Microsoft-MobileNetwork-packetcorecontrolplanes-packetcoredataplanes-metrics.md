---
title: Supported metrics - Microsoft.MobileNetwork/packetcorecontrolplanes/packetcoredataplanes
description: Reference for Microsoft.MobileNetwork/packetcorecontrolplanes/packetcoredataplanes metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 09/04/2023
---
# Supported metrics for Microsoft.MobileNetwork/packetcorecontrolplanes/packetcoredataplanes  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.MobileNetwork/packetcorecontrolplanes/packetcoredataplanes resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Data Plane Bandwidth<p><p>Data plane bandwidth for all traffic types (bits/second). |`DataPlaneBandwidth` |BitsPerSecond |Total |SiteId, Direction, Interface |No|
|Data Plane Packet Drop Rate<p><p>Data plane packet drop rate for all traffic types (packets/sec). |`DataPlanePacketDropRate` |CountPerSecond |Total |SiteId, Cause, Direction, Interface |No|
|Data Plane Packet Rate<p><p>Data plane packet rate for all traffic types (packets/sec). |`DataPlanePacketRate` |CountPerSecond |Total |SiteId, Direction, Interface |No|


<!--Gen Date:  Mon Sep 04 2023 13:11:00 GMT+0300 (Israel Daylight Time)-->