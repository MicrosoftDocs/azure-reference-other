---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.StorageTasks/storageTasks, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Transaction|**Objects operated count**<p><p>The number of objects operated in storage task |`ObjectsOperatedCount` |Count |Total |`AccountName`, `TaskAssignmentId`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Transaction|**Objects failed count**<p><p>The number of objects failed in storage task |`ObjectsOperationFailedCount` |Count |Total |`AccountName`, `TaskAssignmentId`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Transaction|**Objects succeeded count**<p><p>The number of objects succeeded in storage task |`ObjectsOperationSucceededCount` |Count |Total |`AccountName`, `TaskAssignmentId`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Transaction|**Objects targed count**<p><p>The number of objects targeted in storage task |`ObjectsTargetedCount` |Count |Total |`AccountName`, `TaskAssignmentId`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Transaction|**Runs count**<p><p>The number of runs in storage task |`StorageTasksRunCount` |Count |Total |`AccountName`, `TaskAssignmentId`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Transaction|**Runs failed count**<p><p>The number of runs failed in storage task |`StorageTasksRunFailureCount` |Count |Total |`AccountName`, `TaskAssignmentId`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Transaction|**Runs succeeded count**<p><p>The number of runs succeeded in storage task |`StorageTasksRunSuccessCount` |Count |Total |`AccountName`, `TaskAssignmentId`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Transaction|**Runs failed with at least one operation count**<p><p>The number of runs failed with at least one opeartion count in storage task |`StorageTasksRunWithFailedOperationCount` |Count |Total |`AccountName`, `TaskAssignmentId`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|