---
title: Supported metrics - Microsoft.ConnectedCache/ispCustomers
description: Reference for Microsoft.ConnectedCache/ispCustomers metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.ConnectedCache/ispCustomers  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.ConnectedCache/ispCustomers resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Egress Mbps<p><p>Egress Throughput |`egressbps` |BitsPerSecond |Average |cachenodeid |Yes|
|Hit Ratio<p><p>Cache hit ratio is a measurement of how many content requests a cache is able to fill successfully, compared to how many requests it receives. |`hitRatio` |Percent |Average |cachenodeid |Yes|
|Hits<p><p>Count of hits |`hits` |Count |Count |cachenodeid |Yes|
|Hit Mbps<p><p>Hit Throughput |`hitsbps` |BitsPerSecond |Average |cachenodeid |Yes|
|Inbound<p><p>Inbound Throughput |`inboundbps` |BitsPerSecond |Average |cachenodeid |Yes|
|Misses<p><p>Count of misses |`misses` |Count |Count |cachenodeid |Yes|
|Miss Mbps<p><p>Miss Throughput |`missesbps` |BitsPerSecond |Average |cachenodeid |Yes|
|Outbound<p><p>Outbound Throughput |`outboundbps` |BitsPerSecond |Average |cachenodeid |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->