---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: microsoft.bing/accounts, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Blocked Calls**<p><p>Number of calls that exceeded the rate or quota limit |`BlockedCalls` |Count |Total |`ApiName`, `ServingRegion`, `StatusCode`|PT1M |Yes|
|**Client Errors**<p><p>Number of calls with any client error (HTTP status code 4xx) |`ClientErrors` |Count |Total |`ApiName`, `ServingRegion`, `StatusCode`|PT1M |Yes|
|**Data In**<p><p>Incoming request Content-Length in bytes |`DataIn` |Bytes |Total |`ApiName`, `ServingRegion`, `StatusCode`|PT1M |Yes|
|**Data Out**<p><p>Outgoing response Content-Length in bytes |`DataOut` |Bytes |Total |`ApiName`, `ServingRegion`, `StatusCode`|PT1M |Yes|
|**Latency**<p><p>Latency in milliseconds |`Latency` |Milliseconds |Average, Minimum, Maximum |`ApiName`, `ServingRegion`, `StatusCode`|PT1M |Yes|
|**Server Errors**<p><p>Number of calls with any server error (HTTP status code 5xx) |`ServerErrors` |Count |Total |`ApiName`, `ServingRegion`, `StatusCode`|PT1M |Yes|
|**Successful Calls**<p><p>Number of successful calls (HTTP status code 2xx) |`SuccessfulCalls` |Count |Total |`ApiName`, `ServingRegion`, `StatusCode`|PT1M |Yes|
|**Total Calls**<p><p>Total number of calls |`TotalCalls` |Count |Total |`ApiName`, `ServingRegion`, `StatusCode`|PT1M |Yes|
|**Total Errors**<p><p>Number of calls with any error (HTTP status code 4xx or 5xx) |`TotalErrors` |Count |Total |`ApiName`, `ServingRegion`, `StatusCode`|PT1M |Yes|