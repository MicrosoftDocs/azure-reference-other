---
title: Supported metrics - microsoft.bing/accounts
description: Reference for microsoft.bing/accounts metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for microsoft.bing/accounts  
<!-- Data source : naam-->


The following table lists the metrics available for the microsoft.bing/accounts resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Blocked Calls<p><p>Number of calls that exceeded the rate or quota limit |`BlockedCalls` |Count |Total |ApiName, ServingRegion, StatusCode |Yes|
|Client Errors<p><p>Number of calls with any client error (HTTP status code 4xx) |`ClientErrors` |Count |Total |ApiName, ServingRegion, StatusCode |Yes|
|Data In<p><p>Incoming request Content-Length in bytes |`DataIn` |Bytes |Total |ApiName, ServingRegion, StatusCode |Yes|
|Data Out<p><p>Outgoing response Content-Length in bytes |`DataOut` |Bytes |Total |ApiName, ServingRegion, StatusCode |Yes|
|Latency<p><p>Latency in milliseconds |`Latency` |Milliseconds |Average |ApiName, ServingRegion, StatusCode |Yes|
|Server Errors<p><p>Number of calls with any server error (HTTP status code 5xx) |`ServerErrors` |Count |Total |ApiName, ServingRegion, StatusCode |Yes|
|Successful Calls<p><p>Number of successful calls (HTTP status code 2xx) |`SuccessfulCalls` |Count |Total |ApiName, ServingRegion, StatusCode |Yes|
|Total Calls<p><p>Total number of calls |`TotalCalls` |Count |Total |ApiName, ServingRegion, StatusCode |Yes|
|Total Errors<p><p>Number of calls with any error (HTTP status code 4xx or 5xx) |`TotalErrors` |Count |Total |ApiName, ServingRegion, StatusCode |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->