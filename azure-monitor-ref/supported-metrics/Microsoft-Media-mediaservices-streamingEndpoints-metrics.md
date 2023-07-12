---
title: Supported metrics - Microsoft.Media/mediaservices/streamingEndpoints
description: Reference for Microsoft.Media/mediaservices/streamingEndpoints metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Media/mediaservices/streamingEndpoints  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Media/mediaservices/streamingEndpoints resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|CPU usage<p><p>CPU usage for premium streaming endpoints. This data is not available for standard streaming endpoints. |`CPU` |Percent |Average |No Dimensions |Yes|
|Egress<p><p>The amount of Egress data, in bytes. |`Egress` |Bytes |Total |OutputFormat |Yes|
|Egress bandwidth<p><p>Egress bandwidth in bits per second. |`EgressBandwidth` |BitsPerSecond |Average |No Dimensions |No|
|Requests<p><p>Requests to a Streaming Endpoint. |`Requests` |Count |Total |OutputFormat, HttpStatusCode, ErrorCode |Yes|
|Success end to end Latency<p><p>The average latency for successful requests in milliseconds. |`SuccessE2ELatency` |MilliSeconds |Average |OutputFormat |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->