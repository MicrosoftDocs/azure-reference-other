---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.DataFactory/datafactories, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Failed Runs**<p><p>Failed Runs |`FailedRuns` |Count |Total |`pipelineName`, `activityName`|PT1H |Yes|
|**Successful Runs**<p><p>Successful Runs |`SuccessfulRuns` |Count |Total |`pipelineName`, `activityName`|PT1H |Yes|