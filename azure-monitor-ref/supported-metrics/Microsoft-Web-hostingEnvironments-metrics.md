---
title: Supported metrics - Microsoft.Web/hostingEnvironments
description: Reference for Microsoft.Web/hostingEnvironments metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Web/hostingEnvironments  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Web/hostingEnvironments resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Active Requests (deprecated)<p><p>Number of requests being actively handled by the App Service Environment at any given time |`ActiveRequests` |Count |Total |Instance |Yes|
|Average Response Time (deprecated)<p><p>Average time taken for the ASE to serve requests |`AverageResponseTime` |Seconds |Average |Instance |Yes|
|Data In<p><p>Incoming bandwidth used across all front end instances |`BytesReceived` |Bytes |Total |Instance |Yes|
|Data Out<p><p>Outgoing bandwidth used across all front end instances |`BytesSent` |Bytes |Total |Instance |Yes|
|CPU Percentage<p><p>CPU used across all front end instances |`CpuPercentage` |Percent |Average |Instance |Yes|
|Disk Queue Length<p><p>Number of both read and write requests that were queued on storage |`DiskQueueLength` |Count |Average |Instance |Yes|
|Http 101<p><p>Number of requests resulting in an HTTP 101 status code |`Http101` |Count |Total |Instance |Yes|
|Http 2xx<p><p>Number of requests resulting in an HTTP status code ≥ 200 but < 300 |`Http2xx` |Count |Total |Instance |Yes|
|Http 3xx<p><p>Number of requests resulting in an HTTP status code ≥ 300 but < 400 |`Http3xx` |Count |Total |Instance |Yes|
|Http 401<p><p>Number of requests resulting in an HTTP 401 status code |`Http401` |Count |Total |Instance |Yes|
|Http 403<p><p>Number of requests resulting in an HTTP 403 status code |`Http403` |Count |Total |Instance |Yes|
|Http 404<p><p>Number of requests resulting in an HTTP 404 status code |`Http404` |Count |Total |Instance |Yes|
|Http 406<p><p>Number of requests resulting in an HTTP 406 status code |`Http406` |Count |Total |Instance |Yes|
|Http 4xx<p><p>Number of requests resulting in an HTTP status code ≥ 400 but < 500 |`Http4xx` |Count |Total |Instance |Yes|
|Http Server Errors<p><p>Number of requests resulting in an HTTP status code ≥ 500 but < 600 |`Http5xx` |Count |Total |Instance |Yes|
|Http Queue Length<p><p>Number of HTTP requests that had to sit on the queue before being fulfilled |`HttpQueueLength` |Count |Average |Instance |Yes|
|Response Time<p><p>Time taken for the ASE to serve requests |`HttpResponseTime` |Seconds |Average |Instance |Yes|
|Large App Service Plan Workers<p><p>Number of large App Service Plan worker instances |`LargeAppServicePlanInstances` |Count |Average |No Dimensions |Yes|
|Medium App Service Plan Workers<p><p>Number of medium App Service Plan worker instances |`MediumAppServicePlanInstances` |Count |Average |No Dimensions |Yes|
|Memory Percentage<p><p>Memory used across all front end instances |`MemoryPercentage` |Percent |Average |Instance |Yes|
|Requests<p><p>Number of web requests served |`Requests` |Count |Total |Instance |Yes|
|Small App Service Plan Workers<p><p>Number of small App Service Plan worker instances |`SmallAppServicePlanInstances` |Count |Average |No Dimensions |Yes|
|Total Front Ends<p><p>Number of front end instances |`TotalFrontEnds` |Count |Average |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->