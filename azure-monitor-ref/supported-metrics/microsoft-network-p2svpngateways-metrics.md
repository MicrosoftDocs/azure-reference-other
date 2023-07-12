---
title: Supported metrics - microsoft.network/p2svpngateways
description: Reference for microsoft.network/p2svpngateways metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for microsoft.network/p2svpngateways  
<!-- Data source : naam-->


The following table lists the metrics available for the microsoft.network/p2svpngateways resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Gateway P2S Bandwidth<p><p>Point-to-site bandwidth of a gateway in bytes per second |`P2SBandwidth` |BytesPerSecond |Average |Instance |Yes|
|P2S Connection Count<p><p>Point-to-site connection count of a gateway |`P2SConnectionCount` |Count |Total |Protocol, Instance |Yes|
|User Vpn Route Count<p><p>Count of P2S User Vpn routes learned by gateway |`UserVpnRouteCount` |Count |Total |RouteType, Instance |No|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->