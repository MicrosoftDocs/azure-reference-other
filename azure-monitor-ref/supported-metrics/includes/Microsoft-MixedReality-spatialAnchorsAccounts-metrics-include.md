---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.MixedReality/spatialAnchorsAccounts, arm
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Anchors Created<p><p>Number of Anchors created |`AnchorsCreated` |Count |Total |DeviceFamily, SDKVersion|PT5M, PT1H, PT12H, P1D |Yes|
|Anchors Deleted<p><p>Number of Anchors deleted |`AnchorsDeleted` |Count |Total |DeviceFamily, SDKVersion|PT5M, PT1H, PT12H, P1D |Yes|
|Anchors Queried<p><p>Number of Spatial Anchors queried |`AnchorsQueried` |Count |Total |DeviceFamily, SDKVersion|PT5M, PT1H, PT12H, P1D |Yes|
|Anchors Updated<p><p>Number of Anchors updated |`AnchorsUpdated` |Count |Total |DeviceFamily, SDKVersion|PT5M, PT1H, PT12H, P1D |Yes|
|Poses Found<p><p>Number of Poses returned |`PosesFound` |Count |Total |DeviceFamily, SDKVersion|PT5M, PT1H, PT12H, P1D |Yes|
|Total Daily Anchors<p><p>Total number of Anchors - Daily |`TotalDailyAnchors` |Count |Average, Total |DeviceFamily, SDKVersion|P1D |Yes|