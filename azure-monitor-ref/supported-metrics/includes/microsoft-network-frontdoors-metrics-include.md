---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Network/frontdoors, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Backend Health|**Backend Health Percentage**<br><br>The percentage of successful health probes from the HTTP/S proxy to backends |`BackendHealthPercentage` |Percent |Average |`Backend`, `BackendPool`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Traffic|**Backend Request Count**<br><br>The number of requests sent from the HTTP/S proxy to backends |`BackendRequestCount` |Count |Total |`HttpStatus`, `HttpStatusGroup`, `Backend`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Latency|**Backend Request Latency**<br><br>The time calculated from when the request was sent by the HTTP/S proxy to the backend until the HTTP/S proxy received the last response byte from the backend |`BackendRequestLatency` |MilliSeconds |Average |`Backend`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Traffic|**Billable Response Size**<br><br>The number of billable bytes (minimum 2KB per request) sent as responses from HTTP/S proxy to clients. |`BillableResponseSize` |Bytes |Total |`HttpStatus`, `HttpStatusGroup`, `ClientRegion`, `ClientCountry`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Traffic|**Request Count**<br><br>The number of client requests served by the HTTP/S proxy |`RequestCount` |Count |Total |`HttpStatus`, `HttpStatusGroup`, `ClientRegion`, `ClientCountry`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Traffic|**Request Size**<br><br>The number of bytes sent as requests from clients to the HTTP/S proxy |`RequestSize` |Bytes |Total |`HttpStatus`, `HttpStatusGroup`, `ClientRegion`, `ClientCountry`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Traffic|**Response Size**<br><br>The number of bytes sent as responses from HTTP/S proxy to clients |`ResponseSize` |Bytes |Total |`HttpStatus`, `HttpStatusGroup`, `ClientRegion`, `ClientCountry`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Latency|**Total Latency**<br><br>The time calculated from when the client request was received by the HTTP/S proxy until the client acknowledged the last response byte from the HTTP/S proxy |`TotalLatency` |MilliSeconds |Average |`HttpStatus`, `HttpStatusGroup`, `ClientRegion`, `ClientCountry`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Traffic|**Web Application Firewall Request Count**<br><br>The number of client requests processed by the Web Application Firewall |`WebApplicationFirewallRequestCount` |Count |Total |`PolicyName`, `RuleName`, `Action`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|