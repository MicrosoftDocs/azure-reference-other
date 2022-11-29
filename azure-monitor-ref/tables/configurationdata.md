---
title: Azure Monitor Logs reference - ConfigurationData
description: Reference for ConfigurationData table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# ConfigurationData

 View the last reported state for in-guest configuration data such as Files Software Registry Keys Windows Services and Linux Daemons

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
| Architecture | string | Instruction set architecture for the software being tracked |
| Attributes | string |  |
| Computer | string |  |
| ConfigDataType | string | Type of configuration item: Files Software WindowsServices Registry Daemons |
| CurrentVersion | string | Current software version |
| DateCreated | datetime | Created date of the file |
| DateModified | datetime | Last modified date of the file |
| FileContentChecksum | string | Checksum of the reporting file |
| FileSystemPath | string | File system path for the reporting file |
| Hive | string | Registry hive for the reporting registry key |
| Location | string |  |
| ManagementGroupName | string |  |
| Name | string |  |
| Publisher | string | Software publisher name |
| RegistryKey | string | Registy key name |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Size | long | Size of the file |
| SoftwareDescription | string | Description of the software |
| SoftwareName | string | Name of the software |
| SoftwareType | string | Type of the software: Application Package Update |
| SourceComputerId | string |  |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| SvcAccount | string | User account that is associated with the service executable explicitly to provide a security context for the service |
| SvcController | string | Service property that was changed |
| SvcDescription | string | Parent process for the daemon |
| SvcDisplayName | string | Human-frinedly name for the service |
| SvcName | string | Name of the service |
| SvcPath | string | The file path to the executable for the service |
| SvcRunlevels | string | Modes used by the daemon for system operation |
| SvcStartupType | string | Startup behavior of the service |
| SvcState | string | Current state of the service |
| TimeGenerated | datetime | Date and time the record was created. |
| Type | string | The name of the table |
| ValueData | string | Data contained in the value and registry key being tracked |
| ValueName | string | Name of the value for the registry key being tracked |
| ValueType | string | Type of the value for the registry key being tracked |
| VMUUID | string |  |
