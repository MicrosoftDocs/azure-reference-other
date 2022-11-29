---
title: Azure Monitor Logs reference - ConfigurationChange
description: Reference for ConfigurationChange table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# ConfigurationChange

 View changes to in-guest configuration data such as Files Software Registry Keys Windows Services and Linux Daemons

## Categories

- IT & Management Tools
## Solutions

- Change Tracking
## Resource types

- Virtual machines
- VMware
- Azure Stack HCI
- System Center Virtual Machine Manager
- Virtual Machine Scale Sets




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Acls | string | The Access-Control List specifies which users or system processes are granted access to objects |
| Attributes | string |  |
| ChangeCategory | string | The type of change that occurred: Added Removed Modified |
| Computer | string |  |
| ConfigChangeType | string | Type of configuration item that changed: Files Software WindowsServices Registry Daemons |
| Current | string | Current value |
| DateCreated | datetime | Date that the item was created |
| DateModified | datetime | Date that the item was last modified |
| FieldsChanged | string | Fields that were changed as part of the change record |
| FileContentChecksum | string | Checksum of the file content |
| FileSystemPath | string | File system path for the changed file |
| Hive | string | Registry hive for the changed registry key |
| LastSnapshotAge | long | Age of the last snapshot |
| Location | string |  |
| ManagementGroupName | string | Name of a resource's assigned management group |
| Name | string |  |
| Previous | string | Previous value |
| PreviousAcls | string | Previous Acl value |
| PreviousAttributes | string | Previous attributes value |
| PreviousDateCreated | datetime | Previous date created time |
| PreviousDateModified | datetime | Previous date modified time |
| PreviousFileContentChecksum | string | Previous file content checksum value |
| PreviousSize | long | Previous file size |
| PreviousValueData | string | Previous registry value data |
| PreviousValueType | string | Previous registry value type |
| Publisher | string | Software publisher name |
| RegistryKey | string | Registry key name |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Size | long | Current size of the changed file |
| SoftwareDescription | string | Description of the software |
| SoftwareName | string | Name of the software |
| SoftwareType | string | Type of the software: Application Package Update |
| SourceComputerId | string |  |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| SvcAccount | string | User account that is associated with the service executable explicitly to provide a security context for the service |
| SvcChangeType | string | Service property that was changed |
| SvcController | string | Parent process for the daemon |
| SvcDisplayName | string | Human-frinedly name for the service |
| SvcName | string | Name of the service |
| SvcPath | string | The file path to the executable for the service |
| SvcPreviousAccount | string | Previous user account that was associated with the sevice executable |
| SvcPreviousController | string | Previous parent process for the daemon |
| SvcPreviousPath | string | Previous file path to the executable for the service |
| SvcPreviousRunlevels | string | Previous modes used by the daemon for system operation |
| SvcPreviousStartupType | string | Previous startup behavior of the service |
| SvcPreviousState | string | Previous state of the service |
| SvcRunlevels | string | Modes used by the daemon for system operation |
| SvcStartupType | string | Startup behavior of the service |
| SvcState | string | Current state of the service |
| TimeGenerated | datetime | Date and time the record was created. |
| Type | string | The name of the table |
| ValueData | string | Data contained in the value and registry key being tracked |
| ValueName | string | Name of the value for the registry key being tracked |
| ValueType | string | Type of the value for the registry key being tracked |
| VMUUID | string |  |
