---
title: Supported metrics - Microsoft.ConnectedCache/CacheNodes
description: Reference for Microsoft.ConnectedCache/CacheNodes metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.ConnectedCache/CacheNodes  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.ConnectedCache/CacheNodes resource type.

  

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
|Cache Efficiency<p><p>Cache Efficiency |`hitRatio` |Percent |Average |cachenodeid |Yes|
|Hits<p><p>Count of hits |`hits` |Count |Count |cachenodeid |Yes|
|Hit Mbps<p><p>Hit Throughput |`hitsbps` |BitsPerSecond |Average |cachenodeid |Yes|
|Misses<p><p>Count of misses |`misses` |Count |Count |cachenodeid |Yes|
|Miss Mbps<p><p>Miss Throughput |`missesbps` |BitsPerSecond |Average |cachenodeid |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->