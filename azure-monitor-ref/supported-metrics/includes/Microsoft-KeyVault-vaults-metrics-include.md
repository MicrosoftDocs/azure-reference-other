---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.KeyVault/vaults, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Overall Vault Availability<p><p>Vault requests availability |`Availability` |Percent |Average |ActivityType, ActivityName, StatusCode, StatusCodeClass|PT1M |Yes|
|Overall Vault Saturation<p><p>Vault capacity used |`SaturationShoebox` |Percent |Average |ActivityType, ActivityName, TransactionType|PT1M |No|
|Total Service Api Hits<p><p>Number of total service api hits |`ServiceApiHit` |Count |Count |ActivityType, ActivityName|PT1M |Yes|
|Overall Service Api Latency<p><p>Overall latency of service api requests |`ServiceApiLatency` |MilliSeconds |Average |ActivityType, ActivityName, StatusCode, StatusCodeClass|PT1M |Yes|
|Total Service Api Results<p><p>Number of total service api results |`ServiceApiResult` |Count |Count |ActivityType, ActivityName, StatusCode, StatusCodeClass|PT1M |Yes|