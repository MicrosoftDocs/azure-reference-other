---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: microsoft.botservice/botservices, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Request Latency**<p><p>Time taken by the server to process the request |`RequestLatency` |Milliseconds |Total |`Operation`, `Authentication`, `Protocol`, `DataCenter`|PT1M |Yes|
|**Requests Traffic**<p><p>Number of Requests Made |`RequestsTraffic` |Percent |Count |`Operation`, `Authentication`, `Protocol`, `StatusCode`, `StatusCodeClass`, `DataCenter`|PT1M |Yes|