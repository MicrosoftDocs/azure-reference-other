---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Web/hostingEnvironments, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Active Requests (deprecated)**<p><p>Number of requests being actively handled by the App Service Environment at any given time |`ActiveRequests` |Count |Total |`Instance`|PT1M |Yes|
|**Average Response Time (deprecated)**<p><p>Average time taken for the ASE to serve requests |`AverageResponseTime` |Seconds |Average |`Instance`|PT1M |Yes|
|**Data In**<p><p>Incoming bandwidth used across all front end instances |`BytesReceived` |Bytes |Total |`Instance`|PT1M |Yes|
|**Data Out**<p><p>Outgoing bandwidth used across all front end instances |`BytesSent` |Bytes |Total |`Instance`|PT1M |Yes|
|**CPU Percentage**<p><p>CPU used across all front end instances |`CpuPercentage` |Percent |Average |`Instance`|PT1M |Yes|
|**Disk Queue Length**<p><p>Number of both read and write requests that were queued on storage |`DiskQueueLength` |Count |Average |`Instance`|PT1M |Yes|
|**Http 101**<p><p>Number of requests resulting in an HTTP 101 status code |`Http101` |Count |Total |`Instance`|PT1M |Yes|
|**Http 2xx**<p><p>Number of requests resulting in an HTTP status code ≥ 200 but < 300 |`Http2xx` |Count |Total |`Instance`|PT1M |Yes|
|**Http 3xx**<p><p>Number of requests resulting in an HTTP status code ≥ 300 but < 400 |`Http3xx` |Count |Total |`Instance`|PT1M |Yes|
|**Http 401**<p><p>Number of requests resulting in an HTTP 401 status code |`Http401` |Count |Total |`Instance`|PT1M |Yes|
|**Http 403**<p><p>Number of requests resulting in an HTTP 403 status code |`Http403` |Count |Total |`Instance`|PT1M |Yes|
|**Http 404**<p><p>Number of requests resulting in an HTTP 404 status code |`Http404` |Count |Total |`Instance`|PT1M |Yes|
|**Http 406**<p><p>Number of requests resulting in an HTTP 406 status code |`Http406` |Count |Total |`Instance`|PT1M |Yes|
|**Http 4xx**<p><p>Number of requests resulting in an HTTP status code ≥ 400 but < 500 |`Http4xx` |Count |Total |`Instance`|PT1M |Yes|
|**Http Server Errors**<p><p>Number of requests resulting in an HTTP status code ≥ 500 but < 600 |`Http5xx` |Count |Total |`Instance`|PT1M |Yes|
|**Http Queue Length**<p><p>Number of HTTP requests that had to sit on the queue before being fulfilled |`HttpQueueLength` |Count |Average |`Instance`|PT1M |Yes|
|**Response Time**<p><p>Time taken for the ASE to serve requests |`HttpResponseTime` |Seconds |Average |`Instance`|PT1M |Yes|
|**Large App Service Plan Workers**<p><p>Number of large App Service Plan worker instances |`LargeAppServicePlanInstances` |Count |Average |\<none\>|PT1M |Yes|
|**Medium App Service Plan Workers**<p><p>Number of medium App Service Plan worker instances |`MediumAppServicePlanInstances` |Count |Average |\<none\>|PT1M |Yes|
|**Memory Percentage**<p><p>Memory used across all front end instances |`MemoryPercentage` |Percent |Average |`Instance`|PT1M |Yes|
|**Requests**<p><p>Number of web requests served |`Requests` |Count |Total |`Instance`|PT1M |Yes|
|**Small App Service Plan Workers**<p><p>Number of small App Service Plan worker instances |`SmallAppServicePlanInstances` |Count |Average |\<none\>|PT1M |Yes|
|**Total Front Ends**<p><p>Number of front end instances |`TotalFrontEnds` |Count |Average |\<none\>|PT1M |Yes|