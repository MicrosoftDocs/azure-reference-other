---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.App/managedEnvironments, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Cores Quota Limit<p><p>The cores quota limit of managed environment |`EnvCoresQuotaLimit` |Count |Average, Maximum, Minimum |No Dimensions|PT1M |Yes|
|Percentage Cores Used Out Of Limit<p><p>The cores quota utilization of managed environment |`EnvCoresQuotaUtilization` |Percent |Average, Maximum, Minimum |No Dimensions|PT1M |Yes|