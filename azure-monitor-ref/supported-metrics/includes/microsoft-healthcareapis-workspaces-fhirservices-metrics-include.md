---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.HealthcareApis/workspaces/fhirservices, arm
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Availability**<p><p>The availability rate of the service. |`Availability` |Percent |Average |\<none\>|PT1M |Yes|
|**Total Data Size**<p><p>Total size of the data in the backing database, in bytes. |`TotalDataSize` |Bytes |Total |\<none\>|PT1M |Yes|
|**Total Errors**<p><p>The total number of internal server errors encountered by the service. |`TotalErrors` |Count |Sum |`Protocol`, `StatusCode`, `StatusCodeClass`, `StatusCodeText`|PT1M |Yes|
|**Total Latency**<p><p>The response latency of the service. |`TotalLatency` |Milliseconds |Average |`Protocol`|PT1M |Yes|
|**Total Requests**<p><p>The total number of requests received by the service. |`TotalRequests` |Count |Sum |`Protocol`|PT1M |Yes|