---
title: Azure Monitor Logs reference - AddonAzureBackupJobs
description: Reference for AddonAzureBackupJobs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
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
| BackupItemUniqueId | string |  |
| BackupManagementServerUniqueId | string |  |
| BackupManagementType | string |  |
| Category | string |  |
| DataTransferredInMB | real |  |
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
| ResourceId | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SchemaVersion | string |  |
| SourceSystem | string |  |
| State | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
| VaultUniqueId | string |  |
