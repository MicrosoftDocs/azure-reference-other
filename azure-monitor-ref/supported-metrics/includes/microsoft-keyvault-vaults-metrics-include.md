---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.KeyVault/vaults, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Overall Vault Availability**<br><br>Vault requests availability |`Availability` |Percent |Average |`ActivityType`, `ActivityName`, `StatusCode`, `StatusCodeClass`|PT1M |Yes|
|**Overall Vault Saturation**<br><br>Vault capacity used |`SaturationShoebox` |Percent |Average |`ActivityType`, `ActivityName`, `TransactionType`|PT1M |No|
|**Total Service Api Hits**<br><br>Number of total service api hits |`ServiceApiHit` |Count |Count |`ActivityType`, `ActivityName`|PT1M |Yes|
|**Overall Service Api Latency**<br><br>Overall latency of service api requests |`ServiceApiLatency` |MilliSeconds |Average |`ActivityType`, `ActivityName`, `StatusCode`, `StatusCodeClass`|PT1M |Yes|
|**Total Service Api Results**<br><br>Number of total service api results |`ServiceApiResult` |Count |Count |`ActivityType`, `ActivityName`, `StatusCode`, `StatusCodeClass`|PT1M |Yes|