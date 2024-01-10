---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Maps/accounts, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Availability**<p><p>Availability of the APIs |`Availability` |Percent |Average |`ApiCategory`, `ApiName`|PT1M |Yes|
|**Usage**<p><p>Count of API calls |`Usage` |Count |Count |`ApiCategory`, `ApiName`, `ResultType`, `ResponseCode`|PT1M |No|