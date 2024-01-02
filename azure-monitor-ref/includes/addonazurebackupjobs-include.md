---
ms.service: azure-monitor
ms.topic: include
ms.date: 12/04/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: AddonAzureBackupJobs
---


| Column | Type | Description |
|---|---|---|
| AdHocOrScheduledJob | string |   |
| ArchiveTierStorageReplicationType | string |   |
| AzureDataCenter | string |   |
| BackupItemFriendlyName | string |   |
| BackupItemId | string |   |
| BackupItemUniqueId | string |   |
| BackupManagementServerUniqueId | string |   |
| BackupManagementType | string |   |
| _BilledSize | real | The record size in bytes |
| Category | string |   |
| DatasourceFriendlyName | string |   |
| DatasourceResourceId | string |   |
| DatasourceSetFriendlyName | string |   |
| DatasourceSetResourceId | string |   |
| DatasourceSetType | string |   |
| DatasourceType | string |   |
| DataTransferredInMB | real |   |
| ExtendedProperties | dynamic |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| JobDurationInSecs | real |   |
| JobFailureCode | string |   |
| JobOperation | string |   |
| JobOperationSubType | string |   |
| JobStartDateTime | datetime |   |
| JobStatus | string |   |
| JobUniqueId | string |   |
| OperationName | string |   |
| ProtectedContainerUniqueId | string |   |
| RecoveryJobDestination | string |   |
| RecoveryJobRPDateTime | datetime |   |
| RecoveryJobRPLocation | string |   |
| RecoveryLocationType | string |   |
| ResourceGroupName | string |   |
| ResourceId | string |   |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SchemaVersion | string |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| State | string |   |
| StorageReplicationType | string |   |
| SubscriptionId | string |   |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
| VaultName | string |   |
| VaultTags | string |   |
| VaultType | string |   |
| VaultUniqueId | string |   |
