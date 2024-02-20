---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: microsoft.insights/components, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Availability|**Availability**<br><br>Percentage of successfully completed availability tests |`availabilityResults/availabilityPercentage` |Percent |Average |`availabilityResult/name`, `availabilityResult/location`|PT1M |Yes|
|Availability|**Availability tests**<br><br>Count of availability tests |`availabilityResults/count` |Count |Count |`availabilityResult/name`, `availabilityResult/location`, `availabilityResult/success`|PT1M |No|
|Availability|**Availability test duration**<br><br>Availability test duration |`availabilityResults/duration` |MilliSeconds |Average, Maximum, Minimum |`availabilityResult/name`, `availabilityResult/location`, `availabilityResult/success`|PT1M |Yes|
|Browser|**Page load network connect time**<br><br>Time between user request and network connection. Includes DNS lookup and transport connection. |`browserTimings/networkDuration` |MilliSeconds |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Browser|**Client processing time**<br><br>Time between receiving the last byte of a document until the DOM is loaded. Async requests may still be processing. |`browserTimings/processingDuration` |MilliSeconds |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Browser|**Receiving response time**<br><br>Time between the first and last bytes, or until disconnection. |`browserTimings/receiveDuration` |MilliSeconds |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Browser|**Send request time**<br><br>Time between network connection and receiving the first byte. |`browserTimings/sendDuration` |MilliSeconds |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Browser|**Browser page load time**<br><br>Time from user request until DOM, stylesheets, scripts and images are loaded. |`browserTimings/totalDuration` |MilliSeconds |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|Server|**Dependency calls**<br><br>Count of calls made by the application to external resources. |`dependencies/count` |Count |Count |`dependency/type`, `dependency/performanceBucket`, `dependency/success`, `dependency/target`, `dependency/resultCode`, `operation/synthetic`, `cloud/roleInstance`, `cloud/roleName`|PT1M |No|
|Server|**Dependency duration**<br><br>Duration of calls made by the application to external resources. |`dependencies/duration` |MilliSeconds |Average, Maximum, Minimum |`dependency/type`, `dependency/performanceBucket`, `dependency/success`, `dependency/target`, `dependency/resultCode`, `operation/synthetic`, `cloud/roleInstance`, `cloud/roleName`|PT1M |Yes|
|Failures|**Dependency call failures**<br><br>Count of failed dependency calls made by the application to external resources. |`dependencies/failed` |Count |Count |`dependency/type`, `dependency/performanceBucket`, `dependency/success`, `dependency/target`, `dependency/resultCode`, `operation/synthetic`, `cloud/roleInstance`, `cloud/roleName`|PT1M |No|
|Failures|**Browser exceptions**<br><br>Count of uncaught exceptions thrown in the browser. |`exceptions/browser` |Count |Count |`client/isServer`, `cloud/roleName`|PT1M |No|
|Failures|**Exceptions**<br><br>Combined count of all uncaught exceptions. |`exceptions/count` |Count |Count |`cloud/roleName`, `cloud/roleInstance`, `client/type`|PT1M |Yes|
|Failures|**Server exceptions**<br><br>Count of uncaught exceptions thrown in the server application. |`exceptions/server` |Count |Count |`client/isServer`, `cloud/roleName`, `cloud/roleInstance`|PT1M |No|
|Usage|**Page views**<br><br>Count of page views. |`pageViews/count` |Count |Count |`operation/synthetic`, `cloud/roleName`|PT1M |Yes|
|Usage|**Page view load time**<br><br>Page view load time |`pageViews/duration` |MilliSeconds |Average, Maximum, Minimum |`operation/synthetic`, `cloud/roleName`|PT1M |Yes|
|Performance counters|**Exception rate**<br><br>Count of handled and unhandled exceptions reported to windows, including .NET exceptions and unmanaged exceptions that are converted into .NET exceptions. |`performanceCounters/exceptionsPerSecond` |CountPerSecond |Average, Maximum, Minimum |`cloud/roleInstance`|PT1M |Yes|
|Performance counters|**Available memory**<br><br>Physical memory immediately available for allocation to a process or for system use. |`performanceCounters/memoryAvailableBytes` |Bytes |Average, Maximum, Minimum |`cloud/roleInstance`|PT1M |Yes|
|Performance counters|**Process CPU**<br><br>The percentage of elapsed time that all process threads used the processor to execute instructions. This can vary between 0 to 100. This metric indicates the performance of w3wp process alone. |`performanceCounters/processCpuPercentage` |Percent |Average, Maximum, Minimum |`cloud/roleInstance`|PT1M |Yes|
|Performance counters|**Process IO rate**<br><br>Total bytes per second read and written to files, network and devices. |`performanceCounters/processIOBytesPerSecond` |BytesPerSecond |Average, Maximum, Minimum |`cloud/roleInstance`|PT1M |Yes|
|Performance counters|**Processor time**<br><br>The percentage of time that the processor spends in non-idle threads. |`performanceCounters/processorCpuPercentage` |Percent |Average, Maximum, Minimum |`cloud/roleInstance`|PT1M |Yes|
|Performance counters|**Process private bytes**<br><br>Memory exclusively assigned to the monitored application's processes. |`performanceCounters/processPrivateBytes` |Bytes |Average, Maximum, Minimum |`cloud/roleInstance`|PT1M |Yes|
|Performance counters|**HTTP request execution time**<br><br>Execution time of the most recent request. |`performanceCounters/requestExecutionTime` |MilliSeconds |Average, Maximum, Minimum |`cloud/roleInstance`|PT1M |Yes|
|Performance counters|**HTTP requests in application queue**<br><br>Length of the application request queue. |`performanceCounters/requestsInQueue` |Count |Average, Maximum, Minimum |`cloud/roleInstance`|PT1M |Yes|
|Performance counters|**HTTP request rate**<br><br>Rate of all requests to the application per second from ASP.NET. |`performanceCounters/requestsPerSecond` |CountPerSecond |Average, Maximum, Minimum |`cloud/roleInstance`|PT1M |Yes|
|Server|**Server requests**<br><br>Count of HTTP requests completed. |`requests/count` |Count |Count |`request/performanceBucket`, `request/resultCode`, `operation/synthetic`, `cloud/roleInstance`, `request/success`, `cloud/roleName`|PT1M |No|
|Server|**Server response time**<br><br>Time between receiving an HTTP request and finishing sending the response. |`requests/duration` |MilliSeconds |Average, Maximum, Minimum |`request/performanceBucket`, `request/resultCode`, `operation/synthetic`, `cloud/roleInstance`, `request/success`, `cloud/roleName`|PT1M |Yes|
|Failures|**Failed requests**<br><br>Count of HTTP requests marked as failed. In most cases these are requests with a response code >= 400 and not equal to 401. |`requests/failed` |Count |Count |`request/performanceBucket`, `request/resultCode`, `request/success`, `operation/synthetic`, `cloud/roleInstance`, `cloud/roleName`|PT1M |No|
|Server|**Server request rate**<br><br>Rate of server requests per second |`requests/rate` |CountPerSecond |Average |`request/performanceBucket`, `request/resultCode`, `operation/synthetic`, `cloud/roleInstance`, `request/success`, `cloud/roleName`|PT1M |No|
|Usage|**Traces**<br><br>Trace document count |`traces/count` |Count |Count |`trace/severityLevel`, `operation/synthetic`, `cloud/roleName`, `cloud/roleInstance`|PT1M |Yes|