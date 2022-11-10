---
title: Azure Monitor Logs reference - ADReplicationResult
description: Reference for ADReplicationResult table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# ADReplicationResult

 The AD Replication Status solution regularly monitors your Active Directory environment for any replication failures.

## Categories

- Workloads
## Solutions

- AD Replication Status
## Resource types

- Virtual machines
- VMware
- Azure Stack HCI
- System Center Virtual Machine Manager




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AssessmentId | string | Unique Guid corresponding to each run |
| Computer | string | Computer Name where the solution ran |
| ConsecutiveFailures | int | Number of consecutive replication failures between two Domain Controllers |
| DestinationServer | string | AD Replication Destination Server |
| DestinationSiteName | string | AD Replication Destination Site Name |
| HelpLink | string | Help Link for more information |
| IsDestinationGC | bool | Is Destinationation Global Catalog |
| IsSourceGC | bool | Is Source Global Catalog |
| LastAttemptedSync | datetime | Last Attempted Replication DateTime |
| LastSuccessfulSync | datetime | Last Successful DateTime |
| LastSyncMessage | string | Last Replication Sync Message |
| LastSyncResult | int | Last Replication Sync Success / Failure Code |
| PartitionName | string | Partition Name |
| PercentOfTSL | real | Percentage of Tombstone Lifecycle |
| ReplicationNeighborOption | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceInvocationId | string | Unique Id assigned to a Domain Controller |
| SourceServer | string | Source Server Name |
| SourceSiteName | string | Source Site Name |
| SourceSystem | string | Source of the Output |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime | Date and time the record was created. |
| TombstoneLifetime | string | Length of time a deleted object persisted in the database |
| Type | string | The name of the table |
