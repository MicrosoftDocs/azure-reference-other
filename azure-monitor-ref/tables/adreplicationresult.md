---
title: Azure Monitor Logs reference - ADReplicationResult
description: Reference for ADReplicationResult table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# ADReplicationResult

 The AD Replication Status solution regularly monitors your Active Directory environment for any replication failures.

## Categories

- Workloads
## Solutions

- AD Replication Status
## Resource types

- Virtual machine




## Columns

|Column|Type|Description|
|---|---|---|
|TimeGenerated|datetime|Date and time the record was created.|
|LastSyncResult|int|Last Replication Sync Success / Failure Code|
|LastSyncMessage|string|Last Replication Sync Message|
|SourceServer|string|Source Server Name|
|DestinationServer|string|AD Replication Destination Server|
|PartitionName|string|Partition Name|
|LastAttemptedSync|datetime|Last Attempted Replication DateTime|
|LastSuccessfulSync|datetime|Last Successful DateTime|
|ConsecutiveFailures|int|Number of consecutive replication failures between two Domain Controllers|
|HelpLink|string|Help Link for more information|
|TombstoneLifetime|string|Length of time a deleted object persisted in the database|
|PercentOfTSL|real|Percentage of Tombstone Lifecycle|
|IsSourceGC|bool|Is Source Global Catalog|
|IsDestinationGC|bool|Is Destinationation Global Catalog|
|SourceSiteName|string|Source Site Name|
|DestinationSiteName|string|AD Replication Destination Site Name|
|ReplicationNeighborOption|string||
|SourceInvocationId|string|Unique Id assigned to a Domain Controller|
|AssessmentId|string|Unique Guid corresponding to each run|
|SourceSystem|string|Source of the Output|
|Computer|string|Computer Name where the solution ran|
|Type|string||
|_ResourceId|string||
