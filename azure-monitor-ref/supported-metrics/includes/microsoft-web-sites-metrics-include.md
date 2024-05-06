---
ms.service: azure-monitor
ms.topic: include
ms.date: 05/06/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Web/sites, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Always Ready Function Execution Count**<br><br>Always Ready Function Execution Count. For Flex Consumption FunctionApps only. |`AlwaysReadyFunctionExecutionCount` |Count |Total |`Instance`|PT1M |Yes|
|**Always Ready Function Execution Units**<br><br>Always Ready Function Execution Units. For Flex Consumption FunctionApps only. |`AlwaysReadyFunctionExecutionUnits` |Count |Total |`Instance`|PT1M |Yes|
|**Always Ready Units**<br><br>Always Ready Units. For Flex Consumption FunctionApps only. |`AlwaysReadyUnits` |Count |Total |`Instance`|PT1M |Yes|
|**Connections**<br><br>The number of bound sockets existing in the sandbox (w3wp.exe and its child processes). A bound socket is created by calling bind()/connect() APIs and remains until said socket is closed with CloseHandle()/closesocket(). For WebApps and FunctionApps. |`AppConnections` |Count |Average, Count, Maximum, Minimum |`Instance`|PT1M |Yes|
|**Average memory working set**<br><br>The average amount of memory used by the app, in megabytes (MiB). For WebApps and FunctionApps. |`AverageMemoryWorkingSet` |Bytes |Average |`Instance`|PT1M |Yes|
|**Average Response Time (deprecated)**<br><br>The average time taken for the app to serve requests, in seconds. For WebApps and FunctionApps. |`AverageResponseTime` |Seconds |Average |`Instance`|PT1M |Yes|
|**Data In**<br><br>The amount of incoming bandwidth consumed by the app, in MiB. For WebApps and FunctionApps. |`BytesReceived` |Bytes |Total |`Instance`|PT1M |Yes|
|**Data Out**<br><br>The amount of outgoing bandwidth consumed by the app, in MiB. For WebApps and FunctionApps. |`BytesSent` |Bytes |Total |`Instance`|PT1M |Yes|
|**CPU Time**<br><br>The amount of CPU consumed by the app, in seconds. For more information about this metric. Please see https://aka.ms/website-monitor-cpu-time-vs-cpu-percentage (CPU time vs CPU percentage). For WebApps only. |`CpuTime` |Seconds |Count, Total, Minimum, Maximum |`Instance`|PT1M |Yes|
|**Current Assemblies**<br><br>The current number of Assemblies loaded across all AppDomains in this application. For WebApps and FunctionApps. |`CurrentAssemblies` |Count |Average |`Instance`|PT1M |Yes|
|**File System Usage**<br><br>Percentage of filesystem quota consumed by the app. For WebApps and FunctionApps. |`FileSystemUsage` |Bytes |Average |\<none\>|PT6H, PT12H, P1D |Yes|
|**Function Execution Count**<br><br>Function Execution Count. For FunctionApps only. |`FunctionExecutionCount` |Count |Total |`Instance`|PT1M |Yes|
|**Function Execution Units**<br><br>Function Execution Units. For FunctionApps only. |`FunctionExecutionUnits` |Count |Total |`Instance`|PT1M |Yes|
|**Gen 0 Garbage Collections**<br><br>The number of times the generation 0 objects are garbage collected since the start of the app process. Higher generation GCs include all lower generation GCs. For WebApps and FunctionApps. |`Gen0Collections` |Count |Total |`Instance`|PT1M |Yes|
|**Gen 1 Garbage Collections**<br><br>The number of times the generation 1 objects are garbage collected since the start of the app process. Higher generation GCs include all lower generation GCs. For WebApps and FunctionApps. |`Gen1Collections` |Count |Total |`Instance`|PT1M |Yes|
|**Gen 2 Garbage Collections**<br><br>The number of times the generation 2 objects are garbage collected since the start of the app process. For WebApps and FunctionApps. |`Gen2Collections` |Count |Total |`Instance`|PT1M |Yes|
|**Handle Count**<br><br>The total number of handles currently open by the app process. For WebApps and FunctionApps. |`Handles` |Count |Average |`Instance`|PT1M |Yes|
|**Health check status**<br><br>Health check status. For WebApps and FunctionApps. |`HealthCheckStatus` |Count |Average |`Instance`|PT5M, PT1H, P1D |Yes|
|**Http 101**<br><br>The count of requests resulting in an HTTP status code 101. For WebApps and FunctionApps. |`Http101` |Count |Total |`Instance`|PT1M |Yes|
|**Http 2xx**<br><br>The count of requests resulting in an HTTP status code >= 200 but < 300. For WebApps and FunctionApps. |`Http2xx` |Count |Total |`Instance`|PT1M |Yes|
|**Http 3xx**<br><br>The count of requests resulting in an HTTP status code >= 300 but < 400. For WebApps and FunctionApps. |`Http3xx` |Count |Total |`Instance`|PT1M |Yes|
|**Http 401**<br><br>The count of requests resulting in HTTP 401 status code. For WebApps and FunctionApps. |`Http401` |Count |Total |`Instance`|PT1M |Yes|
|**Http 403**<br><br>The count of requests resulting in HTTP 403 status code. For WebApps and FunctionApps. |`Http403` |Count |Total |`Instance`|PT1M |Yes|
|**Http 404**<br><br>The count of requests resulting in HTTP 404 status code. For WebApps and FunctionApps. |`Http404` |Count |Total |`Instance`|PT1M |Yes|
|**Http 406**<br><br>The count of requests resulting in HTTP 406 status code. For WebApps and FunctionApps. |`Http406` |Count |Total |`Instance`|PT1M |Yes|
|**Http 4xx**<br><br>The count of requests resulting in an HTTP status code >= 400 but < 500. For WebApps and FunctionApps. |`Http4xx` |Count |Total |`Instance`|PT1M |Yes|
|**Http Server Errors**<br><br>The count of requests resulting in an HTTP status code >= 500 but < 600. For WebApps and FunctionApps. |`Http5xx` |Count |Total |`Instance`|PT1M |Yes|
|**Response Time**<br><br>The time taken for the app to serve requests, in seconds. For WebApps and FunctionApps. |`HttpResponseTime` |Seconds |Average |`Instance`|PT1M |Yes|
|**Automatic Scaling Instance Count**<br><br>The number of instances on which this app is running. |`InstanceCount` |Count |Average |\<none\>|PT1M |Yes|
|**IO Other Bytes Per Second**<br><br>The rate at which the app process is issuing bytes to I/O operations that don't involve data, such as control operations. For WebApps and FunctionApps. |`IoOtherBytesPerSecond` |BytesPerSecond |Total |`Instance`|PT1M |Yes|
|**IO Other Operations Per Second**<br><br>The rate at which the app process is issuing I/O operations that aren't read or write operations. For WebApps and FunctionApps. |`IoOtherOperationsPerSecond` |BytesPerSecond |Total |`Instance`|PT1M |Yes|
|**IO Read Bytes Per Second**<br><br>The rate at which the app process is reading bytes from I/O operations. For WebApps and FunctionApps. |`IoReadBytesPerSecond` |BytesPerSecond |Total |`Instance`|PT1M |Yes|
|**IO Read Operations Per Second**<br><br>The rate at which the app process is issuing read I/O operations. For WebApps and FunctionApps. |`IoReadOperationsPerSecond` |BytesPerSecond |Total |`Instance`|PT1M |Yes|
|**IO Write Bytes Per Second**<br><br>The rate at which the app process is writing bytes to I/O operations. For WebApps and FunctionApps. |`IoWriteBytesPerSecond` |BytesPerSecond |Total |`Instance`|PT1M |Yes|
|**IO Write Operations Per Second**<br><br>The rate at which the app process is issuing write I/O operations. For WebApps and FunctionApps. |`IoWriteOperationsPerSecond` |BytesPerSecond |Total |`Instance`|PT1M |Yes|
|**Memory working set**<br><br>The current amount of memory used by the app, in MiB. For WebApps and FunctionApps. |`MemoryWorkingSet` |Bytes |Average |`Instance`|PT1M |Yes|
|**On Demand Function Execution Count**<br><br>On Demand Function Execution Count. For Flex Consumption FunctionApps only. |`OnDemandFunctionExecutionCount` |Count |Total |`Instance`|PT1M |Yes|
|**On Demand Function Execution Units**<br><br>On Demand Function Execution Units. For Flex Consumption FunctionApps only. |`OnDemandFunctionExecutionUnits` |Count |Total |`Instance`|PT1M |Yes|
|**Private Bytes**<br><br>Private Bytes is the current size, in bytes, of memory that the app process has allocated that can't be shared with other processes. For WebApps and FunctionApps. |`PrivateBytes` |Bytes |Average |`Instance`|PT1M |Yes|
|**Requests**<br><br>The total number of requests regardless of their resulting HTTP status code. For WebApps and FunctionApps. |`Requests` |Count |Total |`Instance`|PT1M |Yes|
|**Requests In Application Queue**<br><br>The number of requests in the application request queue. For WebApps and FunctionApps. |`RequestsInApplicationQueue` |Count |Average |`Instance`|PT1M |Yes|
|**Thread Count**<br><br>The number of threads currently active in the app process. For WebApps and FunctionApps. |`Threads` |Count |Average |`Instance`|PT1M |Yes|
|**Total App Domains**<br><br>The current number of AppDomains loaded in this application. For WebApps and FunctionApps. |`TotalAppDomains` |Count |Average |`Instance`|PT1M |Yes|
|**Total App Domains Unloaded**<br><br>The total number of AppDomains unloaded since the start of the application. For WebApps and FunctionApps. |`TotalAppDomainsUnloaded` |Count |Average |`Instance`|PT1M |Yes|
|**Workflow Action Completed Count**<br><br>Workflow Action Completed Count. For LogicApps only. |`WorkflowActionsCompleted` |Count |Total |`workflowName`, `status`|PT1M |Yes|
|**Workflow Actions Failure Rate**<br><br>Workflow Actions Failure Rate. For LogicApps only. |`WorkflowActionsFailureRate` |Percent |Total |`workflowName`|PT1M |Yes|
|**Logic App Job Pull Rate Per Second**<br><br>Logic Job Pull Rate per second. For LogicApps only. |`WorkflowAppJobPullRate` |CountPerSecond |Total |`accountName`|PT1M |Yes|
|**Workflow Job Execution Delay**<br><br>Workflow Job Execution Delay. For LogicApps only. |`WorkflowJobExecutionDelay` |Seconds |Average |`workflowName`|PT1M |Yes|
|**Workflow Job Execution Duration**<br><br>Workflow Job Execution Duration. For LogicApps only. |`WorkflowJobExecutionDuration` |Seconds |Average |`workflowName`|PT1M |Yes|
|**Workflow Runs Completed Count**<br><br>Workflow Runs Completed Count. For LogicApps only. |`WorkflowRunsCompleted` |Count |Total |`workflowName`, `status`|PT1M |Yes|
|**Workflow Runs dispatched Count**<br><br>Workflow Runs Dispatched Count. For LogicApps only. |`WorkflowRunsDispatched` |Count |Total |`workflowName`|PT1M |Yes|
|**Workflow Runs Failure Rate**<br><br>Workflow Runs Failure Rate. For LogicApps only. |`WorkflowRunsFailureRate` |Percent |Total |`workflowName`|PT1M |Yes|
|**Workflow Runs Started Count**<br><br>Workflow Runs Started Count. For LogicApps only. |`WorkflowRunsStarted` |Count |Total |`workflowName`|PT1M |Yes|
|**Workflow Triggers Completed Count**<br><br>Workflow Triggers Completed Count. For LogicApps only. |`WorkflowTriggersCompleted` |Count |Total |`workflowName`, `status`|PT1M |Yes|
|**Workflow Triggers Failure Rate**<br><br>Workflow Triggers Failure Rate. For LogicApps only. |`WorkflowTriggersFailureRate` |Percent |Total |`workflowName`|PT1M |Yes|