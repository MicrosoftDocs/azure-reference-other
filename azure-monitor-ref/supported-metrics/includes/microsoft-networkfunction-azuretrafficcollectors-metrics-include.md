---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.NetworkFunction/azureTrafficCollectors, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Performance|**Flow Records**<br><br>Flow Records Processed by ATC. |`count` |Count |Average, Total |`RoleInstance`, `Circuit`|PT1M |Yes|
|Performance|**CPU Usage**<br><br>CPU Usage Percentage. |`usage_active` |Percent |Average, Minimum, Maximum |`Hostname`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Performance|**Memory Usage**<br><br>Memory Usage Percentage. |`used_percent` |Percent |Average |`Hostname`|PT1M |Yes|