---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.MixedReality/spatialAnchorsAccounts, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Capacity|**Anchors Created**<br><br>Number of Anchors created |`AnchorsCreated` |Count |Total |`DeviceFamily`, `SDKVersion`|PT5M, PT1H, PT12H, P1D |Yes|
|Capacity|**Anchors Deleted**<br><br>Number of Anchors deleted |`AnchorsDeleted` |Count |Total |`DeviceFamily`, `SDKVersion`|PT5M, PT1H, PT12H, P1D |Yes|
|Capacity|**Anchors Queried**<br><br>Number of Spatial Anchors queried |`AnchorsQueried` |Count |Total |`DeviceFamily`, `SDKVersion`|PT5M, PT1H, PT12H, P1D |Yes|
|Capacity|**Anchors Updated**<br><br>Number of Anchors updated |`AnchorsUpdated` |Count |Total |`DeviceFamily`, `SDKVersion`|PT5M, PT1H, PT12H, P1D |Yes|
|Capacity|**Poses Found**<br><br>Number of Poses returned |`PosesFound` |Count |Total |`DeviceFamily`, `SDKVersion`|PT5M, PT1H, PT12H, P1D |Yes|
|Capacity|**Total Daily Anchors**<br><br>Total number of Anchors - Daily |`TotalDailyAnchors` |Count |Average, Total |`DeviceFamily`, `SDKVersion`|P1D |Yes|