---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: microsoft.keyvault/managedhsms, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Overall Service Availability**<p><p>Service requests availability |`Availability` |Percent |Average |`ActivityType`, `ActivityName`, `StatusCode`, `StatusCodeClass`|PT1M |No|
|**Total Service Api Hits**<p><p>Number of total service api hits |`ServiceApiHit` |Count |Count |`ActivityType`, `ActivityName`|PT1M |Yes|
|**Overall Service Api Latency**<p><p>Overall latency of service api requests |`ServiceApiLatency` |Milliseconds |Average |`ActivityType`, `ActivityName`, `StatusCode`, `StatusCodeClass`|PT1M |No|