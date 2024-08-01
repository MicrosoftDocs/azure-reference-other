---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: ADReplicationResult
---


| Column | Type | Description |
|---|---|---|
| AssessmentId | string | Unique Guid corresponding to each run |
| _BilledSize | real | The record size in bytes |
| Computer | string | Computer Name where the solution ran |
| ConsecutiveFailures | int | Number of consecutive replication failures between two Domain Controllers |
| DestinationServer | string | AD Replication Destination Server |
| DestinationSiteName | string | AD Replication Destination Site Name |
| HelpLink | string | Help Link for more information |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| IsDestinationGC | bool | Is Destinationation Global Catalog |
| IsSourceGC | bool | Is Source Global Catalog |
| LastAttemptedSync | datetime | Last Attempted Replication DateTime |
| LastSuccessfulSync | datetime | Last Successful DateTime |
| LastSyncMessage | string | Last Replication Sync Message |
| LastSyncResult | int | Last Replication Sync Success / Failure Code |
| PartitionName | string | Partition Name |
| PercentOfTSL | real | Percentage of Tombstone Lifecycle |
| ReplicationNeighborOption | string |   |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceInvocationId | string | Unique Id assigned to a Domain Controller |
| SourceServer | string | Source Server Name |
| SourceSiteName | string | Source Site Name |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime | Date and time the record was created. |
| TombstoneLifetime | string | Length of time a deleted object persisted in the database |
| Type | string | The name of the table |
