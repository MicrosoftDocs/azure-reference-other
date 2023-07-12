---
title: Supported metrics - microsoft.insights/components
description: Reference for microsoft.insights/components metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for microsoft.insights/components  
<!-- Data source : naam-->


The following table lists the metrics available for the microsoft.insights/components resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Availability<p><p>Percentage of successfully completed availability tests |`availabilityResults/availabilityPercentage` |Percent |Average |availabilityResult/name, availabilityResult/location |Yes|
|Availability tests<p><p>Count of availability tests |`availabilityResults/count` |Count |Count |availabilityResult/name, availabilityResult/location, availabilityResult/success |No|
|Availability test duration<p><p>Availability test duration |`availabilityResults/duration` |MilliSeconds |Average |availabilityResult/name, availabilityResult/location, availabilityResult/success |Yes|
|Page load network connect time<p><p>Time between user request and network connection. Includes DNS lookup and transport connection. |`browserTimings/networkDuration` |MilliSeconds |Average |No Dimensions |Yes|
|Client processing time<p><p>Time between receiving the last byte of a document until the DOM is loaded. Async requests may still be processing. |`browserTimings/processingDuration` |MilliSeconds |Average |No Dimensions |Yes|
|Receiving response time<p><p>Time between the first and last bytes, or until disconnection. |`browserTimings/receiveDuration` |MilliSeconds |Average |No Dimensions |Yes|
|Send request time<p><p>Time between network connection and receiving the first byte. |`browserTimings/sendDuration` |MilliSeconds |Average |No Dimensions |Yes|
|Browser page load time<p><p>Time from user request until DOM, stylesheets, scripts and images are loaded. |`browserTimings/totalDuration` |MilliSeconds |Average |No Dimensions |Yes|
|Dependency calls<p><p>Count of calls made by the application to external resources. |`dependencies/count` |Count |Count |dependency/type, dependency/performanceBucket, dependency/success, dependency/target, dependency/resultCode, operation/synthetic, cloud/roleInstance, cloud/roleName |No|
|Dependency duration<p><p>Duration of calls made by the application to external resources. |`dependencies/duration` |MilliSeconds |Average |dependency/type, dependency/performanceBucket, dependency/success, dependency/target, dependency/resultCode, operation/synthetic, cloud/roleInstance, cloud/roleName |Yes|
|Dependency call failures<p><p>Count of failed dependency calls made by the application to external resources. |`dependencies/failed` |Count |Count |dependency/type, dependency/performanceBucket, dependency/success, dependency/target, dependency/resultCode, operation/synthetic, cloud/roleInstance, cloud/roleName |No|
|Browser exceptions<p><p>Count of uncaught exceptions thrown in the browser. |`exceptions/browser` |Count |Count |client/isServer, cloud/roleName |No|
|Exceptions<p><p>Combined count of all uncaught exceptions. |`exceptions/count` |Count |Count |cloud/roleName, cloud/roleInstance, client/type |Yes|
|Server exceptions<p><p>Count of uncaught exceptions thrown in the server application. |`exceptions/server` |Count |Count |client/isServer, cloud/roleName, cloud/roleInstance |No|
|Page views<p><p>Count of page views. |`pageViews/count` |Count |Count |operation/synthetic, cloud/roleName |Yes|
|Page view load time<p><p>Page view load time |`pageViews/duration` |MilliSeconds |Average |operation/synthetic, cloud/roleName |Yes|
|Exception rate<p><p>Count of handled and unhandled exceptions reported to windows, including .NET exceptions and unmanaged exceptions that are converted into .NET exceptions. |`performanceCounters/exceptionsPerSecond` |CountPerSecond |Average |cloud/roleInstance |Yes|
|Available memory<p><p>Physical memory immediately available for allocation to a process or for system use. |`performanceCounters/memoryAvailableBytes` |Bytes |Average |cloud/roleInstance |Yes|
|Process CPU<p><p>The percentage of elapsed time that all process threads used the processor to execute instructions. This can vary between 0 to 100. This metric indicates the performance of w3wp process alone. |`performanceCounters/processCpuPercentage` |Percent |Average |cloud/roleInstance |Yes|
|Process IO rate<p><p>Total bytes per second read and written to files, network and devices. |`performanceCounters/processIOBytesPerSecond` |BytesPerSecond |Average |cloud/roleInstance |Yes|
|Processor time<p><p>The percentage of time that the processor spends in non-idle threads. |`performanceCounters/processorCpuPercentage` |Percent |Average |cloud/roleInstance |Yes|
|Process private bytes<p><p>Memory exclusively assigned to the monitored application's processes. |`performanceCounters/processPrivateBytes` |Bytes |Average |cloud/roleInstance |Yes|
|HTTP request execution time<p><p>Execution time of the most recent request. |`performanceCounters/requestExecutionTime` |MilliSeconds |Average |cloud/roleInstance |Yes|
|HTTP requests in application queue<p><p>Length of the application request queue. |`performanceCounters/requestsInQueue` |Count |Average |cloud/roleInstance |Yes|
|HTTP request rate<p><p>Rate of all requests to the application per second from ASP.NET. |`performanceCounters/requestsPerSecond` |CountPerSecond |Average |cloud/roleInstance |Yes|
|Server requests<p><p>Count of HTTP requests completed. |`requests/count` |Count |Count |request/performanceBucket, request/resultCode, operation/synthetic, cloud/roleInstance, request/success, cloud/roleName |No|
|Server response time<p><p>Time between receiving an HTTP request and finishing sending the response. |`requests/duration` |MilliSeconds |Average |request/performanceBucket, request/resultCode, operation/synthetic, cloud/roleInstance, request/success, cloud/roleName |Yes|
|Failed requests<p><p>Count of HTTP requests marked as failed. In most cases these are requests with a response code >= 400 and not equal to 401. |`requests/failed` |Count |Count |request/performanceBucket, request/resultCode, request/success, operation/synthetic, cloud/roleInstance, cloud/roleName |No|
|Server request rate<p><p>Rate of server requests per second |`requests/rate` |CountPerSecond |Average |request/performanceBucket, request/resultCode, operation/synthetic, cloud/roleInstance, request/success, cloud/roleName |No|
|Traces<p><p>Trace document count |`traces/count` |Count |Count |trace/severityLevel, operation/synthetic, cloud/roleName, cloud/roleInstance |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->