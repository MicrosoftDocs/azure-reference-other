---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Network/frontdoors, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Backend Health Percentage**<p><p>The percentage of successful health probes from the HTTP/S proxy to backends |`BackendHealthPercentage` |Percent |Average |`Backend`, `BackendPool`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Backend Request Count**<p><p>The number of requests sent from the HTTP/S proxy to backends |`BackendRequestCount` |Count |Total |`HttpStatus`, `HttpStatusGroup`, `Backend`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Backend Request Latency**<p><p>The time calculated from when the request was sent by the HTTP/S proxy to the backend until the HTTP/S proxy received the last response byte from the backend |`BackendRequestLatency` |MilliSeconds |Average |`Backend`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Billable Response Size**<p><p>The number of billable bytes (minimum 2KB per request) sent as responses from HTTP/S proxy to clients. |`BillableResponseSize` |Bytes |Total |`HttpStatus`, `HttpStatusGroup`, `ClientRegion`, `ClientCountry`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Request Count**<p><p>The number of client requests served by the HTTP/S proxy |`RequestCount` |Count |Total |`HttpStatus`, `HttpStatusGroup`, `ClientRegion`, `ClientCountry`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Request Size**<p><p>The number of bytes sent as requests from clients to the HTTP/S proxy |`RequestSize` |Bytes |Total |`HttpStatus`, `HttpStatusGroup`, `ClientRegion`, `ClientCountry`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Response Size**<p><p>The number of bytes sent as responses from HTTP/S proxy to clients |`ResponseSize` |Bytes |Total |`HttpStatus`, `HttpStatusGroup`, `ClientRegion`, `ClientCountry`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Total Latency**<p><p>The time calculated from when the client request was received by the HTTP/S proxy until the client acknowledged the last response byte from the HTTP/S proxy |`TotalLatency` |MilliSeconds |Average |`HttpStatus`, `HttpStatusGroup`, `ClientRegion`, `ClientCountry`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Web Application Firewall Request Count**<p><p>The number of client requests processed by the Web Application Firewall |`WebApplicationFirewallRequestCount` |Count |Total |`PolicyName`, `RuleName`, `Action`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|