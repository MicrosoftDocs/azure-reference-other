---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: microsoft.bing/accounts, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Traffic|**Blocked Calls**<br><br>Number of calls that exceeded the rate or quota limit |`BlockedCalls` |Count |Total |`ApiName`, `ServingRegion`, `StatusCode`|PT1M |Yes|
|Errors|**Client Errors**<br><br>Number of calls with any client error (HTTP status code 4xx) |`ClientErrors` |Count |Total |`ApiName`, `ServingRegion`, `StatusCode`|PT1M |Yes|
|Traffic|**Data In**<br><br>Incoming request Content-Length in bytes |`DataIn` |Bytes |Total |`ApiName`, `ServingRegion`, `StatusCode`|PT1M |Yes|
|Traffic|**Data Out**<br><br>Outgoing response Content-Length in bytes |`DataOut` |Bytes |Total |`ApiName`, `ServingRegion`, `StatusCode`|PT1M |Yes|
|Latency|**Latency**<br><br>Latency in milliseconds |`Latency` |Milliseconds |Average, Minimum, Maximum |`ApiName`, `ServingRegion`, `StatusCode`|PT1M |Yes|
|Errors|**Server Errors**<br><br>Number of calls with any server error (HTTP status code 5xx) |`ServerErrors` |Count |Total |`ApiName`, `ServingRegion`, `StatusCode`|PT1M |Yes|
|Traffic|**Successful Calls**<br><br>Number of successful calls (HTTP status code 2xx) |`SuccessfulCalls` |Count |Total |`ApiName`, `ServingRegion`, `StatusCode`|PT1M |Yes|
|Traffic|**Total Calls**<br><br>Total number of calls |`TotalCalls` |Count |Total |`ApiName`, `ServingRegion`, `StatusCode`|PT1M |Yes|
|Errors|**Total Errors**<br><br>Number of calls with any error (HTTP status code 4xx or 5xx) |`TotalErrors` |Count |Total |`ApiName`, `ServingRegion`, `StatusCode`|PT1M |Yes|