---
title: Supported metrics - Microsoft.Web/staticsites
description: Reference for Microsoft.Web/staticsites metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 09/04/2023
---
# Supported metrics for Microsoft.Web/staticsites  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Web/staticsites resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Data Out<p><p>BytesSent |`BytesSent` |Bytes |Total |No Dimensions |Yes|
|CdnPercentageOf4XX<p><p>CdnPercentageOf4XX |`CdnPercentageOf4XX` |Percent |Total |No Dimensions |Yes|
|CdnPercentageOf5XX<p><p>CdnPercentageOf5XX |`CdnPercentageOf5XX` |Percent |Total |No Dimensions |Yes|
|CdnRequestCount<p><p>CdnRequestCount |`CdnRequestCount` |Count |Total |No Dimensions |Yes|
|CdnResponseSize<p><p>CdnResponseSize |`CdnResponseSize` |Bytes |Total |No Dimensions |Yes|
|CdnTotalLatency<p><p>CdnTotalLatency |`CdnTotalLatency` |MilliSeconds |Total |No Dimensions |Yes|
|FunctionErrors<p><p>FunctionErrors |`FunctionErrors` |Count |Total |No Dimensions |Yes|
|FunctionHits<p><p>FunctionHits |`FunctionHits` |Count |Total |No Dimensions |Yes|
|SiteErrors<p><p>SiteErrors |`SiteErrors` |Count |Total |No Dimensions |Yes|
|SiteHits<p><p>SiteHits |`SiteHits` |Count |Total |No Dimensions |Yes|


<!--Gen Date:  Mon Sep 04 2023 13:11:00 GMT+0300 (Israel Daylight Time)-->