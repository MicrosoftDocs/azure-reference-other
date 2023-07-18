---
title: Supported metrics - Microsoft.Cdn/profiles
description: Reference for Microsoft.Cdn/profiles metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Cdn/profiles  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Cdn/profiles resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Byte Hit Ratio<p><p>This is the ratio of the total bytes served from the cache compared to the total response bytes |`ByteHitRatio` |Percent |Average |Endpoint |Yes|
|Origin Health Percentage<p><p>The percentage of successful health probes from AFDX to backends. |`OriginHealthPercentage` |Percent |Average |Origin, OriginGroup |Yes|
|Origin Latency<p><p>The time calculated from when the request was sent by AFDX edge to the backend until AFDX received the last response byte from the backend. |`OriginLatency` |MilliSeconds |Average |Origin, Endpoint |Yes|
|Origin Request Count<p><p>The number of requests sent from AFDX to origin. |`OriginRequestCount` |Count |Total |HttpStatus, HttpStatusGroup, Origin, Endpoint |Yes|
|Percentage of 4XX<p><p>The percentage of all the client requests for which the response status code is 4XX |`Percentage4XX` |Percent |Average |Endpoint, ClientRegion, ClientCountry |Yes|
|Percentage of 5XX<p><p>The percentage of all the client requests for which the response status code is 5XX |`Percentage5XX` |Percent |Average |Endpoint, ClientRegion, ClientCountry |Yes|
|Request Count<p><p>The number of client requests served by the HTTP/S proxy |`RequestCount` |Count |Total |HttpStatus, HttpStatusGroup, ClientRegion, ClientCountry, Endpoint |Yes|
|Request Size<p><p>The number of bytes sent as requests from clients to AFDX. |`RequestSize` |Bytes |Total |HttpStatus, HttpStatusGroup, ClientRegion, ClientCountry, Endpoint |Yes|
|Response Size<p><p>The number of bytes sent as responses from HTTP/S proxy to clients |`ResponseSize` |Bytes |Total |HttpStatus, HttpStatusGroup, ClientRegion, ClientCountry, Endpoint |Yes|
|Total Latency<p><p>The time calculated from when the client request was received by the HTTP/S proxy until the client acknowledged the last response byte from the HTTP/S proxy |`TotalLatency` |MilliSeconds |Average |HttpStatus, HttpStatusGroup, ClientRegion, ClientCountry, Endpoint |Yes|
|Web Application Firewall Request Count<p><p>The number of client requests processed by the Web Application Firewall |`WebApplicationFirewallRequestCount` |Count |Total |PolicyName, RuleName, Action |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->