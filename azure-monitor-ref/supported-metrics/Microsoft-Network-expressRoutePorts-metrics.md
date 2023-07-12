---
title: Supported metrics - Microsoft.Network/expressRoutePorts
description: Reference for Microsoft.Network/expressRoutePorts metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Network/expressRoutePorts  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Network/expressRoutePorts resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|AdminState<p><p>Admin state of the port |`AdminState` |Count |Average |Link |Yes|
|FastPathRoutesCount<p><p>Count of fastpath routes configured on port |`FastPathRoutesCountForDirectPort` |Count |Maximum |No Dimensions |Yes|
|LineProtocol<p><p>Line protocol status of the port |`LineProtocol` |Count |Average |Link |Yes|
|BitsInPerSecond<p><p>Bits ingressing Azure per second |`PortBitsInPerSecond` |BitsPerSecond |Average |Link |No|
|BitsOutPerSecond<p><p>Bits egressing Azure per second |`PortBitsOutPerSecond` |BitsPerSecond |Average |Link |No|
|RxLightLevel<p><p>Rx Light level in dBm |`RxLightLevel` |Count |Average |Link, Lane |Yes|
|TxLightLevel<p><p>Tx light level in dBm |`TxLightLevel` |Count |Average |Link, Lane |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->