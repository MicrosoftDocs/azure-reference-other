---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.NetworkFunction/azureTrafficCollectors, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Flow Records<p><p>Flow Records Processed by ATC. |`count` |Count |Average, Total |RoleInstance|PT1M |Yes|
|CPU Usage<p><p>CPU Usage Percentage. |`usage_active` |Percent |Average, Minimum, Maximum |Hostname|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Memory Usage<p><p>Memory Usage Percentage. |`used_percent` |Percent |Average |Hostname|PT1M |Yes|