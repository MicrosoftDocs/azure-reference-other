---
title: Azure Monitor Logs reference - AddonAzureBackupProtectedInstance
description: Reference for AddonAzureBackupProtectedInstance table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
---

# AddonAzureBackupProtectedInstance

 

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
| ArchiveTierStorageConsumedInMBs | real |  |
| ArchiveTierStorageReplicationType | string |  |
| AzureDataCenter | string |  |
| BackupItemUniqueId | string |  |
| BackupManagementServerUniqueId | string |  |
| BackupManagementType | string |  |
| _BilledSize | real |  |
| BillingGroupFriendlyName | string |  |
| BillingGroupResourceGroupName | string |  |
| BillingGroupType | string |  |
| BillingGroupUniqueId | string |  |
| Category | string |  |
| DatasourceType | string |  |
| _IsBillable | string |  |
| OperationName | string |  |
| ProtectedContainerUniqueId | string |  |
| ProtectedInstanceCount | int |  |
| ResourceGroupName | string |  |
| ResourceId | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SchemaVersion | string |  |
| SourceSizeInMBs | real |  |
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
