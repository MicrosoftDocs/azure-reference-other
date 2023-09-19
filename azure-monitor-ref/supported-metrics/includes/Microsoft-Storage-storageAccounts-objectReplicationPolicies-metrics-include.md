---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Storage/storageAccounts/objectReplicationPolicies, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Pending Bytes for Replication (PREVIEW)<p><p>The size in bytes of the blob object pending for replication, please note, this metric is in preview and is subject to change before becoming generally available |`PendingBytesForReplication` |Bytes |Average, Minimum, Maximum |TimeBucket|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|
|Pending Operations for Replication (PREVIEW)<p><p>The count of pending operations for replication, please note, this metric is in preview and is subject to change before becoming generally available |`PendingOperationsForReplication` |Count |Average, Minimum, Maximum |TimeBucket|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|