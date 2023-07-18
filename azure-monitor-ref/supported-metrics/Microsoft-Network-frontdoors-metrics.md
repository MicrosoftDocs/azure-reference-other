---
title: Supported metrics - Microsoft.Network/frontdoors
description: Reference for Microsoft.Network/frontdoors metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Network/frontdoors  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Network/frontdoors resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Backend Health Percentage<p><p>The percentage of successful health probes from the HTTP/S proxy to backends |`BackendHealthPercentage` |Percent |Average |Backend, BackendPool |Yes|
|Backend Request Count<p><p>The number of requests sent from the HTTP/S proxy to backends |`BackendRequestCount` |Count |Total |HttpStatus, HttpStatusGroup, Backend |Yes|
|Backend Request Latency<p><p>The time calculated from when the request was sent by the HTTP/S proxy to the backend until the HTTP/S proxy received the last response byte from the backend |`BackendRequestLatency` |MilliSeconds |Average |Backend |Yes|
|Billable Response Size<p><p>The number of billable bytes (minimum 2KB per request) sent as responses from HTTP/S proxy to clients. |`BillableResponseSize` |Bytes |Total |HttpStatus, HttpStatusGroup, ClientRegion, ClientCountry |Yes|
|Request Count<p><p>The number of client requests served by the HTTP/S proxy |`RequestCount` |Count |Total |HttpStatus, HttpStatusGroup, ClientRegion, ClientCountry |Yes|
|Request Size<p><p>The number of bytes sent as requests from clients to the HTTP/S proxy |`RequestSize` |Bytes |Total |HttpStatus, HttpStatusGroup, ClientRegion, ClientCountry |Yes|
|Response Size<p><p>The number of bytes sent as responses from HTTP/S proxy to clients |`ResponseSize` |Bytes |Total |HttpStatus, HttpStatusGroup, ClientRegion, ClientCountry |Yes|
|Total Latency<p><p>The time calculated from when the client request was received by the HTTP/S proxy until the client acknowledged the last response byte from the HTTP/S proxy |`TotalLatency` |MilliSeconds |Average |HttpStatus, HttpStatusGroup, ClientRegion, ClientCountry |Yes|
|Web Application Firewall Request Count<p><p>The number of client requests processed by the Web Application Firewall |`WebApplicationFirewallRequestCount` |Count |Total |PolicyName, RuleName, Action |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->