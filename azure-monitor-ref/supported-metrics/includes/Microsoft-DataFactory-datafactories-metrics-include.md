---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.DataFactory/datafactories, arm
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Failed Runs<p><p>Failed Runs |`FailedRuns` |Count |Total |pipelineName, activityName|PT1H |Yes|
|Successful Runs<p><p>Successful Runs |`SuccessfulRuns` |Count |Total |pipelineName, activityName|PT1H |Yes|