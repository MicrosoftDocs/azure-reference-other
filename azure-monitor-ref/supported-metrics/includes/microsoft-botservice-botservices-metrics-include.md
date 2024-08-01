---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: microsoft.botservice/botservices, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Latency|**Request Latency**<br><br>Time taken by the server to process the request |`RequestLatency` |Milliseconds |Total |`Operation`, `Authentication`, `Protocol`, `DataCenter`|PT1M |Yes|
|Traffic|**Requests Traffic**<br><br>Number of Requests Made |`RequestsTraffic` |Percent |Count |`Operation`, `Authentication`, `Protocol`, `StatusCode`, `StatusCodeClass`, `DataCenter`|PT1M |Yes|