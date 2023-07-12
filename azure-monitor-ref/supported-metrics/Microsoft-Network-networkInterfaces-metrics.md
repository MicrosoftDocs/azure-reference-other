---
title: Supported metrics - Microsoft.Network/networkInterfaces
description: Reference for Microsoft.Network/networkInterfaces metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Network/networkInterfaces  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.Network/networkInterfaces resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Bytes Received<p><p>Number of bytes the Network Interface received |`BytesReceivedRate` |Bytes |Total |No Dimensions |Yes|
|Bytes Sent<p><p>Number of bytes the Network Interface sent |`BytesSentRate` |Bytes |Total |No Dimensions |Yes|
|Packets Received<p><p>Number of packets the Network Interface received |`PacketsReceivedRate` |Count |Total |No Dimensions |Yes|
|Packets Sent<p><p>Number of packets the Network Interface sent |`PacketsSentRate` |Count |Total |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->