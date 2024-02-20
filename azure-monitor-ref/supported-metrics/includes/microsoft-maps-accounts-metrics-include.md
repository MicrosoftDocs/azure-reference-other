---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Maps/accounts, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Availability**<br><br>Availability of the APIs |`Availability` |Percent |Average |`ApiCategory`, `ApiName`|PT1M |Yes|
|**Creator Usage**<br><br>Azure Maps Creator usage statistics |`CreatorUsage` |Bytes |Average |`ServiceName`|PT1M |No|
|**Usage**<br><br>Count of API calls |`Usage` |Count |Count |`ApiCategory`, `ApiName`, `ResultType`, `ResponseCode`|PT1M |No|