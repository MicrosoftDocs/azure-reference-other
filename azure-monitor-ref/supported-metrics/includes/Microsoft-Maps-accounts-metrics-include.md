---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Maps/accounts, arm
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Availability<p><p>Availability of the APIs |`Availability` |Percent |Average |ApiCategory, ApiName|PT1M |Yes|
|Usage<p><p>Count of API calls |`Usage` |Count |Count |ApiCategory, ApiName, ResultType, ResponseCode|PT1M |No|