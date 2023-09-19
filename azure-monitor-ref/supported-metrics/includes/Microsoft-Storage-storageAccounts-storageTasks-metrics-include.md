---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Storage/storageAccounts/storageTasks, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Objects operated count<p><p>The number of objects operated in storage task |`ObjectsOperatedCount` |Count |Total |AccountName, TaskAssignmentId|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Objects failed count<p><p>The number of objects failed in storage task |`ObjectsOperationFailedCount` |Count |Total |AccountName, TaskAssignmentId|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Objects targed count<p><p>The number of objects targeted in storage task |`ObjectsTargetedCount` |Count |Total |AccountName, TaskAssignmentId|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|