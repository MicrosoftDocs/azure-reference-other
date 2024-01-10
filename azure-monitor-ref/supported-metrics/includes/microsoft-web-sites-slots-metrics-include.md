---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Web/sites/slots, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Connections**<p><p>The number of bound sockets existing in the sandbox (w3wp.exe and its child processes). A bound socket is created by calling bind()/connect() APIs and remains until said socket is closed with CloseHandle()/closesocket(). |`AppConnections` |Count |Average, Count, Maximum, Minimum |`Instance`|PT1M |Yes|
|**Average memory working set**<p><p>The average amount of memory used by the app, in megabytes (MiB). |`AverageMemoryWorkingSet` |Bytes |Average |`Instance`|PT1M |Yes|
|**Average Response Time (deprecated)**<p><p>The average time taken for the app to serve requests, in seconds. |`AverageResponseTime` |Seconds |Average |`Instance`|PT1M |Yes|
|**Data In**<p><p>The amount of incoming bandwidth consumed by the app, in MiB. |`BytesReceived` |Bytes |Total |`Instance`|PT1M |Yes|
|**Data Out**<p><p>The amount of outgoing bandwidth consumed by the app, in MiB. |`BytesSent` |Bytes |Total |`Instance`|PT1M |Yes|
|**CPU Time**<p><p>The amount of CPU consumed by the app, in seconds. For more information about this metric. Please see https://aka.ms/website-monitor-cpu-time-vs-cpu-percentage (CPU time vs CPU percentage). |`CpuTime` |Seconds |Count, Total, Minimum, Maximum |`Instance`|PT1M |Yes|
|**Current Assemblies**<p><p>The current number of Assemblies loaded across all AppDomains in this application. |`CurrentAssemblies` |Count |Average |`Instance`|PT1M |Yes|
|**File System Usage**<p><p>Percentage of filesystem quota consumed by the app. |`FileSystemUsage` |Bytes |Average |\<none\>|PT6H, PT12H, P1D |Yes|
|**Function Execution Count**<p><p>Function Execution Count |`FunctionExecutionCount` |Count |Total |`Instance`|PT1M |Yes|
|**Function Execution Units**<p><p>Function Execution Units |`FunctionExecutionUnits` |Count |Total |`Instance`|PT1M |Yes|
|**Gen 0 Garbage Collections**<p><p>The number of times the generation 0 objects are garbage collected since the start of the app process. Higher generation GCs include all lower generation GCs. |`Gen0Collections` |Count |Total |`Instance`|PT1M |Yes|
|**Gen 1 Garbage Collections**<p><p>The number of times the generation 1 objects are garbage collected since the start of the app process. Higher generation GCs include all lower generation GCs. |`Gen1Collections` |Count |Total |`Instance`|PT1M |Yes|
|**Gen 2 Garbage Collections**<p><p>The number of times the generation 2 objects are garbage collected since the start of the app process. |`Gen2Collections` |Count |Total |`Instance`|PT1M |Yes|
|**Handle Count**<p><p>The total number of handles currently open by the app process. |`Handles` |Count |Average |`Instance`|PT1M |Yes|
|**Health check status**<p><p>Health check status |`HealthCheckStatus` |Count |Average |`Instance`|PT5M, PT1H, P1D |Yes|
|**Http 101**<p><p>The count of requests resulting in an HTTP status code 101. |`Http101` |Count |Total |`Instance`|PT1M |Yes|
|**Http 2xx**<p><p>The count of requests resulting in an HTTP status code >= 200 but < 300. |`Http2xx` |Count |Total |`Instance`|PT1M |Yes|
|**Http 3xx**<p><p>The count of requests resulting in an HTTP status code >= 300 but < 400. |`Http3xx` |Count |Total |`Instance`|PT1M |Yes|
|**Http 401**<p><p>The count of requests resulting in HTTP 401 status code. |`Http401` |Count |Total |`Instance`|PT1M |Yes|
|**Http 403**<p><p>The count of requests resulting in HTTP 403 status code. |`Http403` |Count |Total |`Instance`|PT1M |Yes|
|**Http 404**<p><p>The count of requests resulting in HTTP 404 status code. |`Http404` |Count |Total |`Instance`|PT1M |Yes|
|**Http 406**<p><p>The count of requests resulting in HTTP 406 status code. |`Http406` |Count |Total |`Instance`|PT1M |Yes|
|**Http 4xx**<p><p>The count of requests resulting in an HTTP status code >= 400 but < 500. |`Http4xx` |Count |Total |`Instance`|PT1M |Yes|
|**Http Server Errors**<p><p>The count of requests resulting in an HTTP status code >= 500 but < 600. |`Http5xx` |Count |Total |`Instance`|PT1M |Yes|
|**Response Time**<p><p>The time taken for the app to serve requests, in seconds. |`HttpResponseTime` |Seconds |Average |`Instance`|PT1M |Yes|
|**IO Other Bytes Per Second**<p><p>The rate at which the app process is issuing bytes to I/O operations that don't involve data, such as control operations. |`IoOtherBytesPerSecond` |BytesPerSecond |Total |`Instance`|PT1M |Yes|
|**IO Other Operations Per Second**<p><p>The rate at which the app process is issuing I/O operations that aren't read or write operations. |`IoOtherOperationsPerSecond` |BytesPerSecond |Total |`Instance`|PT1M |Yes|
|**IO Read Bytes Per Second**<p><p>The rate at which the app process is reading bytes from I/O operations. |`IoReadBytesPerSecond` |BytesPerSecond |Total |`Instance`|PT1M |Yes|
|**IO Read Operations Per Second**<p><p>The rate at which the app process is issuing read I/O operations. |`IoReadOperationsPerSecond` |BytesPerSecond |Total |`Instance`|PT1M |Yes|
|**IO Write Bytes Per Second**<p><p>The rate at which the app process is writing bytes to I/O operations. |`IoWriteBytesPerSecond` |BytesPerSecond |Total |`Instance`|PT1M |Yes|
|**IO Write Operations Per Second**<p><p>The rate at which the app process is issuing write I/O operations. |`IoWriteOperationsPerSecond` |BytesPerSecond |Total |`Instance`|PT1M |Yes|
|**Memory working set**<p><p>The current amount of memory used by the app, in MiB. |`MemoryWorkingSet` |Bytes |Average |`Instance`|PT1M |Yes|
|**Private Bytes**<p><p>Private Bytes is the current size, in bytes, of memory that the app process has allocated that can't be shared with other processes. |`PrivateBytes` |Bytes |Average |`Instance`|PT1M |Yes|
|**Requests**<p><p>The total number of requests regardless of their resulting HTTP status code. |`Requests` |Count |Total |`Instance`|PT1M |Yes|
|**Requests In Application Queue**<p><p>The number of requests in the application request queue. |`RequestsInApplicationQueue` |Count |Average |`Instance`|PT1M |Yes|
|**Thread Count**<p><p>The number of threads currently active in the app process. |`Threads` |Count |Average |`Instance`|PT1M |Yes|
|**Total App Domains**<p><p>The current number of AppDomains loaded in this application. |`TotalAppDomains` |Count |Average |`Instance`|PT1M |Yes|
|**Total App Domains Unloaded**<p><p>The total number of AppDomains unloaded since the start of the application. |`TotalAppDomainsUnloaded` |Count |Average |`Instance`|PT1M |Yes|