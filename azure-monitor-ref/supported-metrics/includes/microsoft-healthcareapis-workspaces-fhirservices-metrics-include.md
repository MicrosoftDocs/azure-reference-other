---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.HealthcareApis/workspaces/fhirservices, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Availability|**Availability**<br><br>The availability rate of the service. |`Availability` |Percent |Average |\<none\>|PT1M |Yes|
|Saturation|**Total Data Size**<br><br>Total size of the data in the backing database, in bytes. |`TotalDataSize` |Bytes |Total |\<none\>|PT1M |Yes|
|Errors|**Total Errors**<br><br>The total number of internal server errors encountered by the service. |`TotalErrors` |Count |Sum |`Protocol`, `StatusCode`, `StatusCodeClass`, `StatusCodeText`|PT1M |Yes|
|Traffic|**Total Latency**<br><br>The response latency of the service. |`TotalLatency` |Milliseconds |Average |`Protocol`|PT1M |Yes|
|Traffic|**Total Requests**<br><br>The total number of requests received by the service. |`TotalRequests` |Count |Sum |`Protocol`|PT1M |Yes|