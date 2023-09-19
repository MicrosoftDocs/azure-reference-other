---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.NetApp/netAppAccounts/capacityPools, arm
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Pool Allocated Size<p><p>Provisioned size of this pool |`VolumePoolAllocatedSize` |Bytes |Average, Total |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Pool allocated throughput<p><p>Sum of the throughput of all the volumes belonging to the pool |`VolumePoolAllocatedToVolumeThroughput` |BytesPerSecond |Average |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Pool Allocated To Volume Size<p><p>Allocated used size of the pool |`VolumePoolAllocatedUsed` |Bytes |Average |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Provisioned throughput for the pool<p><p>Provisioned throughput of this pool |`VolumePoolProvisionedThroughput` |BytesPerSecond |Average |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Pool Consumed Size<p><p>Sum of the logical size of all the volumes belonging to the pool |`VolumePoolTotalLogicalSize` |Bytes |Average, Total |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Total Snapshot size for the pool<p><p>Sum of snapshot size of all volumes in this pool |`VolumePoolTotalSnapshotSize` |Bytes |Average |No Dimensions|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|