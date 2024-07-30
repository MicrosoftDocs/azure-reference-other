---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.Web/hostingEnvironments, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Active Requests (deprecated)**<br><br>Number of requests being actively handled by the App Service Environment at any given time |`ActiveRequests` |Count |Total |`Instance`|PT1M |Yes|
|**Average Response Time (deprecated)**<br><br>Average time taken for the ASE to serve requests |`AverageResponseTime` |Seconds |Average |`Instance`|PT1M |Yes|
|**Data In**<br><br>Incoming bandwidth used across all front end instances |`BytesReceived` |Bytes |Total |`Instance`|PT1M |Yes|
|**Data Out**<br><br>Outgoing bandwidth used across all front end instances |`BytesSent` |Bytes |Total |`Instance`|PT1M |Yes|
|**CPU Percentage**<br><br>CPU used across all front end instances |`CpuPercentage` |Percent |Average |`Instance`|PT1M |Yes|
|**Disk Queue Length**<br><br>Number of both read and write requests that were queued on storage |`DiskQueueLength` |Count |Average |`Instance`|PT1M |Yes|
|**Http 101**<br><br>Number of requests resulting in an HTTP 101 status code |`Http101` |Count |Total |`Instance`|PT1M |Yes|
|**Http 2xx**<br><br>Number of requests resulting in an HTTP status code ≥ 200 but < 300 |`Http2xx` |Count |Total |`Instance`|PT1M |Yes|
|**Http 3xx**<br><br>Number of requests resulting in an HTTP status code ≥ 300 but < 400 |`Http3xx` |Count |Total |`Instance`|PT1M |Yes|
|**Http 401**<br><br>Number of requests resulting in an HTTP 401 status code |`Http401` |Count |Total |`Instance`|PT1M |Yes|
|**Http 403**<br><br>Number of requests resulting in an HTTP 403 status code |`Http403` |Count |Total |`Instance`|PT1M |Yes|
|**Http 404**<br><br>Number of requests resulting in an HTTP 404 status code |`Http404` |Count |Total |`Instance`|PT1M |Yes|
|**Http 406**<br><br>Number of requests resulting in an HTTP 406 status code |`Http406` |Count |Total |`Instance`|PT1M |Yes|
|**Http 4xx**<br><br>Number of requests resulting in an HTTP status code ≥ 400 but < 500 |`Http4xx` |Count |Total |`Instance`|PT1M |Yes|
|**Http Server Errors**<br><br>Number of requests resulting in an HTTP status code ≥ 500 but < 600 |`Http5xx` |Count |Total |`Instance`|PT1M |Yes|
|**Http Queue Length**<br><br>Number of HTTP requests that had to sit on the queue before being fulfilled |`HttpQueueLength` |Count |Average |`Instance`|PT1M |Yes|
|**Response Time**<br><br>Time taken for the ASE to serve requests |`HttpResponseTime` |Seconds |Average |`Instance`|PT1M |Yes|
|**Large App Service Plan Workers**<br><br>Number of large App Service Plan worker instances |`LargeAppServicePlanInstances` |Count |Average |\<none\>|PT1M |Yes|
|**Medium App Service Plan Workers**<br><br>Number of medium App Service Plan worker instances |`MediumAppServicePlanInstances` |Count |Average |\<none\>|PT1M |Yes|
|**Memory Percentage**<br><br>Memory used across all front end instances |`MemoryPercentage` |Percent |Average |`Instance`|PT1M |Yes|
|**Requests**<br><br>Number of web requests served |`Requests` |Count |Total |`Instance`|PT1M |Yes|
|**Small App Service Plan Workers**<br><br>Number of small App Service Plan worker instances |`SmallAppServicePlanInstances` |Count |Average |\<none\>|PT1M |Yes|
|**Total Front Ends**<br><br>Number of front end instances |`TotalFrontEnds` |Count |Average |\<none\>|PT1M |Yes|