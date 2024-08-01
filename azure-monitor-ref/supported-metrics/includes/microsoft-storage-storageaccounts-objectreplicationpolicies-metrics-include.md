---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.Storage/storageAccounts/objectReplicationPolicies, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Pending Work (PREVIEW)|**Pending Bytes for Replication (PREVIEW)**<br><br>The size in bytes of the blob object pending for replication, please note, this metric is in preview and is subject to change before becoming generally available |`PendingBytesForReplication` |Bytes |Average, Minimum, Maximum |`TimeBucket`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|
|Pending Work (PREVIEW)|**Pending Operations for Replication (PREVIEW)**<br><br>The count of pending operations for replication, please note, this metric is in preview and is subject to change before becoming generally available |`PendingOperationsForReplication` |Count |Average, Minimum, Maximum |`TimeBucket`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|