---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.MixedReality/remoteRenderingAccounts, arm
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Active Rendering Sessions<p><p>Total number of active rendering sessions |`ActiveRenderingSessions` |Count |Average, Minimum, Maximum |SessionType, SDKVersion|PT1M, PT5M, PT1H, PT12H, P1D |Yes|
|Assets Converted<p><p>Total number of assets converted |`AssetsConverted` |Count |Total |SDKVersion|PT1M, PT5M, PT1H, PT12H, P1D |Yes|