---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.MixedReality/spatialAnchorsAccounts, arm
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Anchors Created**<p><p>Number of Anchors created |`AnchorsCreated` |Count |Total |`DeviceFamily`, `SDKVersion`|PT5M, PT1H, PT12H, P1D |Yes|
|**Anchors Deleted**<p><p>Number of Anchors deleted |`AnchorsDeleted` |Count |Total |`DeviceFamily`, `SDKVersion`|PT5M, PT1H, PT12H, P1D |Yes|
|**Anchors Queried**<p><p>Number of Spatial Anchors queried |`AnchorsQueried` |Count |Total |`DeviceFamily`, `SDKVersion`|PT5M, PT1H, PT12H, P1D |Yes|
|**Anchors Updated**<p><p>Number of Anchors updated |`AnchorsUpdated` |Count |Total |`DeviceFamily`, `SDKVersion`|PT5M, PT1H, PT12H, P1D |Yes|
|**Poses Found**<p><p>Number of Poses returned |`PosesFound` |Count |Total |`DeviceFamily`, `SDKVersion`|PT5M, PT1H, PT12H, P1D |Yes|
|**Total Daily Anchors**<p><p>Total number of Anchors - Daily |`TotalDailyAnchors` |Count |Average, Total |`DeviceFamily`, `SDKVersion`|P1D |Yes|