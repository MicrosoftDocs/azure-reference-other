---
title: Azure Monitor Logs reference - AddonAzureBackupJobs
description: Reference for AddonAzureBackupJobs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/13/2023
---

# AddonAzureBackupJobs

 

## Categories

- IT & Management Tools
- Azure Resources
## Solutions

- LogManagement
## Resource types

- Recovery Services Vaults




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AdHocOrScheduledJob | string |  |
| ArchiveTierStorageReplicationType | string |  |
| AzureDataCenter | string |  |
| BackupItemFriendlyName | string |  |
| BackupItemId | string |  |
| BackupItemUniqueId | string |  |
| BackupManagementServerUniqueId | string |  |
| BackupManagementType | string |  |
| _BilledSize | real |  |
| Category | string |  |
| DatasourceFriendlyName | string |  |
| DatasourceResourceId | string |  |
| DatasourceSetFriendlyName | string |  |
| DatasourceSetResourceId | string |  |
| DatasourceSetType | string |  |
| DatasourceType | string |  |
| DataTransferredInMB | real |  |
| _IsBillable | string |  |
| JobDurationInSecs | real |  |
| JobFailureCode | string |  |
| JobOperation | string |  |
| JobOperationSubType | string |  |
| JobStartDateTime | datetime |  |
| JobStatus | string |  |
| JobUniqueId | string |  |
| OperationName | string |  |
| ProtectedContainerUniqueId | string |  |
| RecoveryJobDestination | string |  |
| RecoveryJobRPDateTime | datetime |  |
| RecoveryJobRPLocation | string |  |
| RecoveryLocationType | string |  |
| ResourceGroupName | string |  |
| ResourceId | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SchemaVersion | string |  |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| State | string |  |
| StorageReplicationType | string |  |
| SubscriptionId | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
| VaultName | string |  |
| VaultTags | string |  |
| VaultType | string |  |
| VaultUniqueId | string |  |
