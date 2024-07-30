---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.Cdn/profiles, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Request Status|**Byte Hit Ratio**<br><br>This is the ratio of the total bytes served from the cache compared to the total response bytes |`ByteHitRatio` |Percent |Average |`Endpoint`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Origin Health|**Origin Health Percentage**<br><br>The percentage of successful health probes from AFDX to backends. |`OriginHealthPercentage` |Percent |Average |`Origin`, `OriginGroup`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Latency|**Origin Latency**<br><br>The time calculated from when the request was sent by AFDX edge to the backend until AFDX received the last response byte from the backend. |`OriginLatency` |MilliSeconds |Average |`Origin`, `Endpoint`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Traffic|**Origin Request Count**<br><br>The number of requests sent from AFDX to origin. |`OriginRequestCount` |Count |Total |`HttpStatus`, `HttpStatusGroup`, `Origin`, `Endpoint`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Request Status|**Percentage of 4XX**<br><br>The percentage of all the client requests for which the response status code is 4XX |`Percentage4XX` |Percent |Average |`Endpoint`, `ClientRegion`, `ClientCountry`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Request Status|**Percentage of 5XX**<br><br>The percentage of all the client requests for which the response status code is 5XX |`Percentage5XX` |Percent |Average |`Endpoint`, `ClientRegion`, `ClientCountry`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Traffic|**Request Count**<br><br>The number of client requests served by the HTTP/S proxy |`RequestCount` |Count |Total |`HttpStatus`, `HttpStatusGroup`, `ClientRegion`, `ClientCountry`, `Endpoint`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Traffic|**Request Size**<br><br>The number of bytes sent as requests from clients to AFDX. |`RequestSize` |Bytes |Total |`HttpStatus`, `HttpStatusGroup`, `ClientRegion`, `ClientCountry`, `Endpoint`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Traffic|**Response Size**<br><br>The number of bytes sent as responses from HTTP/S proxy to clients |`ResponseSize` |Bytes |Total |`HttpStatus`, `HttpStatusGroup`, `ClientRegion`, `ClientCountry`, `Endpoint`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Latency|**Total Latency**<br><br>The time calculated from when the client request was received by the HTTP/S proxy until the client acknowledged the last response byte from the HTTP/S proxy |`TotalLatency` |MilliSeconds |Average |`HttpStatus`, `HttpStatusGroup`, `ClientRegion`, `ClientCountry`, `Endpoint`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Traffic|**Web Application Firewall JS Challenge Request Count**<br><br>The number of JS challenge requests evaluated by the Web Application Firewall |`WebApplicationFirewallJsRequestCount` |Count |Total |`PolicyName`, `RuleName`, `Action`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Traffic|**Web Application Firewall Request Count**<br><br>The number of client requests processed by the Web Application Firewall |`WebApplicationFirewallRequestCount` |Count |Total |`PolicyName`, `RuleName`, `Action`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|