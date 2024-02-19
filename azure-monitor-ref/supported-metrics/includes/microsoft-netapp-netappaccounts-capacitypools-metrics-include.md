---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.NetApp/netAppAccounts/capacityPools, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Pool Allocated Size**<br><br>Provisioned size of this pool |`VolumePoolAllocatedSize` |Bytes |Average, Total |\<none\>|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Pool allocated throughput**<br><br>Sum of the throughput of all the volumes belonging to the pool |`VolumePoolAllocatedToVolumeThroughput` |BytesPerSecond |Average |\<none\>|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Pool Allocated To Volume Size**<br><br>Allocated used size of the pool |`VolumePoolAllocatedUsed` |Bytes |Average |\<none\>|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Provisioned throughput for the pool**<br><br>Provisioned throughput of this pool |`VolumePoolProvisionedThroughput` |BytesPerSecond |Average |\<none\>|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Pool Consumed Size**<br><br>Sum of the logical size of all the volumes belonging to the pool |`VolumePoolTotalLogicalSize` |Bytes |Average, Total |\<none\>|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Total Snapshot size for the pool**<br><br>Sum of snapshot size of all volumes in this pool |`VolumePoolTotalSnapshotSize` |Bytes |Average |\<none\>|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|