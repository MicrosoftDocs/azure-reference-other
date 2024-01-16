---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Web/hostingenvironments/multirolepools, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Active Requests (deprecated)**<p><p>Active Requests |`ActiveRequests` |Count |Total |`Instance`|PT1M |Yes|
|**Average Response Time (deprecated)**<p><p>The average time taken for the front end to serve requests, in seconds. |`AverageResponseTime` |Seconds |Average |`Instance`|PT1M |Yes|
|**Data In**<p><p>The average incoming bandwidth used across all front ends, in MiB. |`BytesReceived` |Bytes |Total |`Instance`|PT1M |Yes|
|**Data Out**<p><p>The average incoming bandwidth used across all front end, in MiB. |`BytesSent` |Bytes |Total |`Instance`|PT1M |Yes|
|**CPU Percentage**<p><p>The average CPU used across all instances of front end. |`CpuPercentage` |Percent |Average |`Instance`|PT1M |Yes|
|**Disk Queue Length**<p><p>The average number of both read and write requests that were queued on storage. A high disk queue length is an indication of an app that might be slowing down because of excessive disk I/O. |`DiskQueueLength` |Count |Average |`Instance`|PT1M |Yes|
|**Http 101**<p><p>The count of requests resulting in an HTTP status code 101. |`Http101` |Count |Total |`Instance`|PT1M |Yes|
|**Http 2xx**<p><p>The count of requests resulting in an HTTP status code ≥ 200 but < 300. |`Http2xx` |Count |Total |`Instance`|PT1M |Yes|
|**Http 3xx**<p><p>The count of requests resulting in an HTTP status code ≥ 300 but < 400. |`Http3xx` |Count |Total |`Instance`|PT1M |Yes|
|**Http 401**<p><p>The count of requests resulting in HTTP 401 status code. |`Http401` |Count |Total |`Instance`|PT1M |Yes|
|**Http 403**<p><p>The count of requests resulting in HTTP 403 status code. |`Http403` |Count |Total |`Instance`|PT1M |Yes|
|**Http 404**<p><p>The count of requests resulting in HTTP 404 status code. |`Http404` |Count |Total |`Instance`|PT1M |Yes|
|**Http 406**<p><p>The count of requests resulting in HTTP 406 status code. |`Http406` |Count |Total |`Instance`|PT1M |Yes|
|**Http 4xx**<p><p>The count of requests resulting in an HTTP status code ≥ 400 but < 500. |`Http4xx` |Count |Total |`Instance`|PT1M |Yes|
|**Http Server Errors**<p><p>The count of requests resulting in an HTTP status code ≥ 500 but < 600. |`Http5xx` |Count |Total |`Instance`|PT1M |Yes|
|**Http Queue Length**<p><p>The average number of HTTP requests that had to sit on the queue before being fulfilled. A high or increasing HTTP Queue length is a symptom of a plan under heavy load. |`HttpQueueLength` |Count |Average |`Instance`|PT1M |Yes|
|**Response Time**<p><p>The time taken for the front end to serve requests, in seconds. |`HttpResponseTime` |Seconds |Average |`Instance`|PT1M |Yes|
|**Large App Service Plan Workers**<p><p>Large App Service Plan Workers |`LargeAppServicePlanInstances` |Count |Average |\<none\>|PT1M |Yes|
|**Medium App Service Plan Workers**<p><p>Medium App Service Plan Workers |`MediumAppServicePlanInstances` |Count |Average |\<none\>|PT1M |Yes|
|**Memory Percentage**<p><p>The average memory used across all instances of front end. |`MemoryPercentage` |Percent |Average |`Instance`|PT1M |Yes|
|**Requests**<p><p>The total number of requests regardless of their resulting HTTP status code. |`Requests` |Count |Total |`Instance`|PT1M |Yes|
|**Small App Service Plan Workers**<p><p>Small App Service Plan Workers |`SmallAppServicePlanInstances` |Count |Average |\<none\>|PT1M |Yes|
|**Total Front Ends**<p><p>Total Front Ends |`TotalFrontEnds` |Count |Average |\<none\>|PT1M |Yes|