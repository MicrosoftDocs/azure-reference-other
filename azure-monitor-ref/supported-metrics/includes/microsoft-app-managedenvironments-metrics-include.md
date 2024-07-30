---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.App/managedEnvironments, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Cores Quota Limit**<br><br>The cores quota limit of managed environment |`EnvCoresQuotaLimit` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Percentage Cores Used Out Of Limit**<br><br>The cores quota utilization of managed environment |`EnvCoresQuotaUtilization` |Percent |Average, Maximum, Minimum |\<none\>|PT1M |Yes|