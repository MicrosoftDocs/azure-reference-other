---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Cdn/profiles, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Byte Hit Ratio**<p><p>This is the ratio of the total bytes served from the cache compared to the total response bytes |`ByteHitRatio` |Percent |Average |`Endpoint`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Origin Health Percentage**<p><p>The percentage of successful health probes from AFDX to backends. |`OriginHealthPercentage` |Percent |Average |`Origin`, `OriginGroup`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Origin Latency**<p><p>The time calculated from when the request was sent by AFDX edge to the backend until AFDX received the last response byte from the backend. |`OriginLatency` |MilliSeconds |Average |`Origin`, `Endpoint`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Origin Request Count**<p><p>The number of requests sent from AFDX to origin. |`OriginRequestCount` |Count |Total |`HttpStatus`, `HttpStatusGroup`, `Origin`, `Endpoint`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Percentage of 4XX**<p><p>The percentage of all the client requests for which the response status code is 4XX |`Percentage4XX` |Percent |Average |`Endpoint`, `ClientRegion`, `ClientCountry`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Percentage of 5XX**<p><p>The percentage of all the client requests for which the response status code is 5XX |`Percentage5XX` |Percent |Average |`Endpoint`, `ClientRegion`, `ClientCountry`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Request Count**<p><p>The number of client requests served by the HTTP/S proxy |`RequestCount` |Count |Total |`HttpStatus`, `HttpStatusGroup`, `ClientRegion`, `ClientCountry`, `Endpoint`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Request Size**<p><p>The number of bytes sent as requests from clients to AFDX. |`RequestSize` |Bytes |Total |`HttpStatus`, `HttpStatusGroup`, `ClientRegion`, `ClientCountry`, `Endpoint`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Response Size**<p><p>The number of bytes sent as responses from HTTP/S proxy to clients |`ResponseSize` |Bytes |Total |`HttpStatus`, `HttpStatusGroup`, `ClientRegion`, `ClientCountry`, `Endpoint`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Total Latency**<p><p>The time calculated from when the client request was received by the HTTP/S proxy until the client acknowledged the last response byte from the HTTP/S proxy |`TotalLatency` |MilliSeconds |Average |`HttpStatus`, `HttpStatusGroup`, `ClientRegion`, `ClientCountry`, `Endpoint`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Web Application Firewall Request Count**<p><p>The number of client requests processed by the Web Application Firewall |`WebApplicationFirewallRequestCount` |Count |Total |`PolicyName`, `RuleName`, `Action`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|