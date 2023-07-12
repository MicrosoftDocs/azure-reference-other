---
title: Supported metrics - Microsoft.Web/hostingenvironments/multirolepools
description: Reference for Microsoft.Web/hostingenvironments/multirolepools metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Web/hostingenvironments/multirolepools  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Web/hostingenvironments/multirolepools resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Active Requests (deprecated)<p><p>Active Requests |`ActiveRequests` |Count |Total |Instance |Yes|
|Average Response Time (deprecated)<p><p>The average time taken for the front end to serve requests, in seconds. |`AverageResponseTime` |Seconds |Average |Instance |Yes|
|Data In<p><p>The average incoming bandwidth used across all front ends, in MiB. |`BytesReceived` |Bytes |Total |Instance |Yes|
|Data Out<p><p>The average incoming bandwidth used across all front end, in MiB. |`BytesSent` |Bytes |Total |Instance |Yes|
|CPU Percentage<p><p>The average CPU used across all instances of front end. |`CpuPercentage` |Percent |Average |Instance |Yes|
|Disk Queue Length<p><p>The average number of both read and write requests that were queued on storage. A high disk queue length is an indication of an app that might be slowing down because of excessive disk I/O. |`DiskQueueLength` |Count |Average |Instance |Yes|
|Http 101<p><p>The count of requests resulting in an HTTP status code 101. |`Http101` |Count |Total |Instance |Yes|
|Http 2xx<p><p>The count of requests resulting in an HTTP status code ≥ 200 but < 300. |`Http2xx` |Count |Total |Instance |Yes|
|Http 3xx<p><p>The count of requests resulting in an HTTP status code ≥ 300 but < 400. |`Http3xx` |Count |Total |Instance |Yes|
|Http 401<p><p>The count of requests resulting in HTTP 401 status code. |`Http401` |Count |Total |Instance |Yes|
|Http 403<p><p>The count of requests resulting in HTTP 403 status code. |`Http403` |Count |Total |Instance |Yes|
|Http 404<p><p>The count of requests resulting in HTTP 404 status code. |`Http404` |Count |Total |Instance |Yes|
|Http 406<p><p>The count of requests resulting in HTTP 406 status code. |`Http406` |Count |Total |Instance |Yes|
|Http 4xx<p><p>The count of requests resulting in an HTTP status code ≥ 400 but < 500. |`Http4xx` |Count |Total |Instance |Yes|
|Http Server Errors<p><p>The count of requests resulting in an HTTP status code ≥ 500 but < 600. |`Http5xx` |Count |Total |Instance |Yes|
|Http Queue Length<p><p>The average number of HTTP requests that had to sit on the queue before being fulfilled. A high or increasing HTTP Queue length is a symptom of a plan under heavy load. |`HttpQueueLength` |Count |Average |Instance |Yes|
|Response Time<p><p>The time taken for the front end to serve requests, in seconds. |`HttpResponseTime` |Seconds |Average |Instance |Yes|
|Large App Service Plan Workers<p><p>Large App Service Plan Workers |`LargeAppServicePlanInstances` |Count |Average |No Dimensions |Yes|
|Medium App Service Plan Workers<p><p>Medium App Service Plan Workers |`MediumAppServicePlanInstances` |Count |Average |No Dimensions |Yes|
|Memory Percentage<p><p>The average memory used across all instances of front end. |`MemoryPercentage` |Percent |Average |Instance |Yes|
|Requests<p><p>The total number of requests regardless of their resulting HTTP status code. |`Requests` |Count |Total |Instance |Yes|
|Small App Service Plan Workers<p><p>Small App Service Plan Workers |`SmallAppServicePlanInstances` |Count |Average |No Dimensions |Yes|
|Total Front Ends<p><p>Total Front Ends |`TotalFrontEnds` |Count |Average |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->