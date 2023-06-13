---
title: Azure Monitor Logs reference - CoreAzureBackup
description: Reference for CoreAzureBackup table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/13/2023
---

# CoreAzureBackup

 

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
| AgentVersion | string |  |
| ArchiveTierLatestRecoveryPointLocation | string |  |
| ArchiveTierLatestRecoveryPointTime | datetime |  |
| ArchiveTierOldestRecoveryPointLocation | string |  |
| ArchiveTierOldestRecoveryPointTime | datetime |  |
| ArchiveTierStorageConsumedInMBs | real |  |
| ArchiveTierStorageReplicationType | string |  |
| AzureBackupAgentVersion | string |  |
| AzureDataCenter | string |  |
| BackupItemAppVersion | string |  |
| BackupItemFriendlyName | string |  |
| BackupItemFrontEndSize | real |  |
| BackupItemId | string |  |
| BackupItemName | string |  |
| BackupItemProtectionState | string |  |
| BackupItemType | string |  |
| BackupItemUniqueId | string |  |
| BackupManagementServerName | string |  |
| BackupManagementServerOSVersion | string |  |
| BackupManagementServerType | string |  |
| BackupManagementServerUniqueId | string |  |
| BackupManagementServerVersion | string |  |
| BackupManagementType | string |  |
| _BilledSize | real |  |
| BillingGroupFriendlyName | string |  |
| BillingGroupUniqueId | string |  |
| Category | string |  |
| DatasourceFriendlyName | string |  |
| DatasourceResourceGroupName | string |  |
| DatasourceResourceId | string |  |
| DatasourceSetFriendlyName | string |  |
| DatasourceSetResourceId | string |  |
| DatasourceSetType | string |  |
| DatasourceSubscriptionId | string |  |
| DatasourceType | string |  |
| IsArchiveEnabled | bool |  |
| _IsBillable | string |  |
| LatestRecoveryPointLocation | string |  |
| LatestRecoveryPointTime | datetime |  |
| OldestRecoveryPointLocation | string |  |
| OldestRecoveryPointTime | datetime |  |
| OperationName | string |  |
| PolicyId | string |  |
| PolicyName | string |  |
| PolicyUniqueId | string |  |
| ProtectedContainerFriendlyName | string |  |
| ProtectedContainerLocation | string |  |
| ProtectedContainerName | string |  |
| ProtectedContainerOSType | string |  |
| ProtectedContainerOSVersion | string |  |
| ProtectedContainerProtectionState | string |  |
| ProtectedContainerType | string |  |
| ProtectedContainerUniqueId | string |  |
| ProtectedContainerWorkloadType | string |  |
| ProtectionGroupName | string |  |
| ResourceGroupName | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResourceId | string |  |
| SchemaVersion | string |  |
| SecondaryBackupProtectionState | string |  |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| State | string |  |
| StorageConsumedInMBs | real |  |
| StorageReplicationType | string |  |
| SubscriptionId | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
| VaultName | string |  |
| VaultTags | string |  |
| VaultType | string |  |
| VaultUniqueId | string |  |
