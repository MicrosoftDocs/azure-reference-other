---
title: Supported metrics - Microsoft.Network/dnsResolvers
description: Reference for Microsoft.Network/dnsResolvers metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Network/dnsResolvers  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Network/dnsResolvers resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Inbound Endpoint Count<p><p>This metric indicates the number of inbound endpoints created for a DNS Resolver. |`InboundEndpointCount` |Count |Maximum |No Dimensions |No|
|Outbound Endpoint Count<p><p>This metric indicates the number of outbound endpoints created for a DNS Resolver. |`OutboundEndpointCount` |Count |Maximum |No Dimensions |No|
|Queries Per Second<p><p>This metric indicates the queries per second for a DNS Resolver. (Can be aggregated per EndpointId) |`QPS` |Count |Average |EndpointId |No|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->