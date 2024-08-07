---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.HealthModel/healthmodels, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Latency|**Query execution duration**<br><br>Overall duration of executing all configured queries in parallel and calculating the model health state. |`ExecutionDuration` |Milliseconds |Average, Minimum, Maximum |\<none\>|PT1M |Yes|
|Availability|**Health score per node**<br><br>Health score per node in the model. Dimension splitting should be applied. Can be a value between 0 and 100 percent. Update frequency depends on the refreshInterval of the health model. Does not include the root node. |`NodeHealthScore` |Percent |Average, Minimum, Maximum |`NodeName`|PT1M |Yes|
|Availability|**Overall health score**<br><br>The health score of the root node represents the overall health of the model. Can be a value between 0 and 100 percent. Update frequency depends on the refreshInterval of the health model. |`OverallHealthScore` |Percent |Average, Minimum, Maximum |\<none\>|PT1M |Yes|