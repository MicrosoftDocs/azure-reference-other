---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: microsoft.botservice/botservices, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Latency|**Request Latency**<p><p>Time taken by the server to process the request |`RequestLatency` |Milliseconds |Total |`Operation`, `Authentication`, `Protocol`, `DataCenter`|PT1M |Yes|
|Traffic|**Requests Traffic**<p><p>Number of Requests Made |`RequestsTraffic` |Percent |Count |`Operation`, `Authentication`, `Protocol`, `StatusCode`, `StatusCodeClass`, `DataCenter`|PT1M |Yes|