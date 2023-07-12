---
title: Supported metrics - Microsoft.Network/natGateways
description: Reference for Microsoft.Network/natGateways metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Network/natGateways  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.Network/natGateways resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Bytes<p><p>Total number of Bytes transmitted within time period |`ByteCount` |Bytes |Total |Protocol, Direction |No|
|Datapath Availability (Preview)<p><p>NAT Gateway Datapath Availability |`DatapathAvailability` |Count |Average |No Dimensions |No|
|Packets<p><p>Total number of Packets transmitted within time period |`PacketCount` |Count |Total |Protocol, Direction |No|
|Dropped Packets<p><p>Count of dropped packets |`PacketDropCount` |Count |Total |No Dimensions |No|
|SNAT Connection Count<p><p>Total concurrent active connections |`SNATConnectionCount` |Count |Total |Protocol, ConnectionState |No|
|Total SNAT Connection Count<p><p>Total number of active SNAT connections |`TotalConnectionCount` |Count |Total |Protocol |No|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->