---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: microsoft.insights/components, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Availability<p><p>Percentage of successfully completed availability tests |`availabilityResults/availabilityPercentage` |Percent |Average |availabilityResult/name, availabilityResult/location|PT1M |Yes|
|Availability tests<p><p>Count of availability tests |`availabilityResults/count` |Count |Count |availabilityResult/name, availabilityResult/location, availabilityResult/success|PT1M |No|
|Availability test duration<p><p>Availability test duration |`availabilityResults/duration` |MilliSeconds |Average, Maximum, Minimum |availabilityResult/name, availabilityResult/location, availabilityResult/success|PT1M |Yes|
|Page load network connect time<p><p>Time between user request and network connection. Includes DNS lookup and transport connection. |`browserTimings/networkDuration` |MilliSeconds |Average, Maximum, Minimum |No Dimensions|PT1M |Yes|
|Client processing time<p><p>Time between receiving the last byte of a document until the DOM is loaded. Async requests may still be processing. |`browserTimings/processingDuration` |MilliSeconds |Average, Maximum, Minimum |No Dimensions|PT1M |Yes|
|Receiving response time<p><p>Time between the first and last bytes, or until disconnection. |`browserTimings/receiveDuration` |MilliSeconds |Average, Maximum, Minimum |No Dimensions|PT1M |Yes|
|Send request time<p><p>Time between network connection and receiving the first byte. |`browserTimings/sendDuration` |MilliSeconds |Average, Maximum, Minimum |No Dimensions|PT1M |Yes|
|Browser page load time<p><p>Time from user request until DOM, stylesheets, scripts and images are loaded. |`browserTimings/totalDuration` |MilliSeconds |Average, Maximum, Minimum |No Dimensions|PT1M |Yes|
|Dependency calls<p><p>Count of calls made by the application to external resources. |`dependencies/count` |Count |Count |dependency/type, dependency/performanceBucket, dependency/success, dependency/target, dependency/resultCode, operation/synthetic, cloud/roleInstance, cloud/roleName|PT1M |No|
|Dependency duration<p><p>Duration of calls made by the application to external resources. |`dependencies/duration` |MilliSeconds |Average, Maximum, Minimum |dependency/type, dependency/performanceBucket, dependency/success, dependency/target, dependency/resultCode, operation/synthetic, cloud/roleInstance, cloud/roleName|PT1M |Yes|
|Dependency call failures<p><p>Count of failed dependency calls made by the application to external resources. |`dependencies/failed` |Count |Count |dependency/type, dependency/performanceBucket, dependency/success, dependency/target, dependency/resultCode, operation/synthetic, cloud/roleInstance, cloud/roleName|PT1M |No|
|Browser exceptions<p><p>Count of uncaught exceptions thrown in the browser. |`exceptions/browser` |Count |Count |client/isServer, cloud/roleName|PT1M |No|
|Exceptions<p><p>Combined count of all uncaught exceptions. |`exceptions/count` |Count |Count |cloud/roleName, cloud/roleInstance, client/type|PT1M |Yes|
|Server exceptions<p><p>Count of uncaught exceptions thrown in the server application. |`exceptions/server` |Count |Count |client/isServer, cloud/roleName, cloud/roleInstance|PT1M |No|
|Page views<p><p>Count of page views. |`pageViews/count` |Count |Count |operation/synthetic, cloud/roleName|PT1M |Yes|
|Page view load time<p><p>Page view load time |`pageViews/duration` |MilliSeconds |Average, Maximum, Minimum |operation/synthetic, cloud/roleName|PT1M |Yes|
|Exception rate<p><p>Count of handled and unhandled exceptions reported to windows, including .NET exceptions and unmanaged exceptions that are converted into .NET exceptions. |`performanceCounters/exceptionsPerSecond` |CountPerSecond |Average, Maximum, Minimum |cloud/roleInstance|PT1M |Yes|
|Available memory<p><p>Physical memory immediately available for allocation to a process or for system use. |`performanceCounters/memoryAvailableBytes` |Bytes |Average, Maximum, Minimum |cloud/roleInstance|PT1M |Yes|
|Process CPU<p><p>The percentage of elapsed time that all process threads used the processor to execute instructions. This can vary between 0 to 100. This metric indicates the performance of w3wp process alone. |`performanceCounters/processCpuPercentage` |Percent |Average, Maximum, Minimum |cloud/roleInstance|PT1M |Yes|
|Process IO rate<p><p>Total bytes per second read and written to files, network and devices. |`performanceCounters/processIOBytesPerSecond` |BytesPerSecond |Average, Maximum, Minimum |cloud/roleInstance|PT1M |Yes|
|Processor time<p><p>The percentage of time that the processor spends in non-idle threads. |`performanceCounters/processorCpuPercentage` |Percent |Average, Maximum, Minimum |cloud/roleInstance|PT1M |Yes|
|Process private bytes<p><p>Memory exclusively assigned to the monitored application's processes. |`performanceCounters/processPrivateBytes` |Bytes |Average, Maximum, Minimum |cloud/roleInstance|PT1M |Yes|
|HTTP request execution time<p><p>Execution time of the most recent request. |`performanceCounters/requestExecutionTime` |MilliSeconds |Average, Maximum, Minimum |cloud/roleInstance|PT1M |Yes|
|HTTP requests in application queue<p><p>Length of the application request queue. |`performanceCounters/requestsInQueue` |Count |Average, Maximum, Minimum |cloud/roleInstance|PT1M |Yes|
|HTTP request rate<p><p>Rate of all requests to the application per second from ASP.NET. |`performanceCounters/requestsPerSecond` |CountPerSecond |Average, Maximum, Minimum |cloud/roleInstance|PT1M |Yes|
|Server requests<p><p>Count of HTTP requests completed. |`requests/count` |Count |Count |request/performanceBucket, request/resultCode, operation/synthetic, cloud/roleInstance, request/success, cloud/roleName|PT1M |No|
|Server response time<p><p>Time between receiving an HTTP request and finishing sending the response. |`requests/duration` |MilliSeconds |Average, Maximum, Minimum |request/performanceBucket, request/resultCode, operation/synthetic, cloud/roleInstance, request/success, cloud/roleName|PT1M |Yes|
|Failed requests<p><p>Count of HTTP requests marked as failed. In most cases these are requests with a response code >= 400 and not equal to 401. |`requests/failed` |Count |Count |request/performanceBucket, request/resultCode, request/success, operation/synthetic, cloud/roleInstance, cloud/roleName|PT1M |No|
|Server request rate<p><p>Rate of server requests per second |`requests/rate` |CountPerSecond |Average |request/performanceBucket, request/resultCode, operation/synthetic, cloud/roleInstance, request/success, cloud/roleName|PT1M |No|
|Traces<p><p>Trace document count |`traces/count` |Count |Count |trace/severityLevel, operation/synthetic, cloud/roleName, cloud/roleInstance|PT1M |Yes|