---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.DataFactory/datafactories, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Failed Runs**<br><br>Failed Runs |`FailedRuns` |Count |Total |`pipelineName`, `activityName`|PT1H |Yes|
|**Successful Runs**<br><br>Successful Runs |`SuccessfulRuns` |Count |Total |`pipelineName`, `activityName`|PT1H |Yes|