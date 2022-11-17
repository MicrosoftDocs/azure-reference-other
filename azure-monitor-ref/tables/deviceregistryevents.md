---
title: Azure Monitor Logs reference - DeviceRegistryEvents
description: Reference for DeviceRegistryEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
---

# DeviceRegistryEvents

 This table is part of Microsoft Defender for Endpoints with Azure Sentinel. This table contains Creation and modification of registry entries.

## Categories

- Security
## Solutions

- Microsoft Sentinel




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ActionType | string | Type of activity that triggered the event. |
| AppGuardContainerId | string | Identifier for the virtualized container used by Application Guard to isolate browser activity. |
| DeviceId | string | Unique identifier for the device in the service. |
| DeviceName | string | Fully qualified domain name (FQDN) of the device. |
| InitiatingProcessAccountDomain | string | Domain of the account that ran the process responsible for the event. |
| InitiatingProcessAccountName | string | User name of the account that ran the process responsible for the event. |
| InitiatingProcessAccountObjectId | string | Azure AD object ID of the user account that ran the process responsible for the event. |
| InitiatingProcessAccountSid | string | Security Identifier (SID) of the account that ran the process responsible for the event. |
| InitiatingProcessAccountUpn | string | User principal name (UPN) of the account that ran the process responsible for the event. |
| InitiatingProcessCommandLine | string | Command line used to run the process that initiated the event. |
| InitiatingProcessCreationTime | datetime | Date and time when the process that initiated the event was started. |
| InitiatingProcessFileName | string | Name of the process that initiated the event. |
| InitiatingProcessFolderPath | string | Folder containing the process (image file) that initiated the event. |
| InitiatingProcessId | long | Process ID (PID) of the process that initiated the event. |
| InitiatingProcessIntegrityLevel | string | Integrity level of the process that initiated the event. Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download. These integrity levels influence permissions to resources.. |
| InitiatingProcessMD5 | string | MD5 hash of the process (image file) that initiated the event. |
| InitiatingProcessParentCreationTime | datetime | Date and time when the parent of the process responsible for the event was started. |
| InitiatingProcessParentFileName | string | Name of the parent process that spawned the process responsible for the event. |
| InitiatingProcessParentId | long | Process ID (PID) of the parent process that spawned the process responsible for the event. |
| InitiatingProcessSHA1 | string | SHA-1 hash of the process (image file) that initiated the event. |
| InitiatingProcessSHA256 | string | SHA-256 hash of the process (image file) that initiated the event. This field is usually not populated - use the SHA1 column when available.. |
| InitiatingProcessTokenElevation | string | Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event. |
| MachineGroup | string | Machine group of the machine. This group is used by role-based access control to determine access to the machine. |
| PreviousRegistryKey | string | Original registry key before it was modified. |
| PreviousRegistryValueData | string | Original data of the registry value before it was modified. |
| PreviousRegistryValueName | string | Original name of the registry value before it was modified. |
| RegistryKey | string | Registry key that the recorded action was applied to. |
| RegistryValueData | string | Data of the registry value that the recorded action was applied to. |
| RegistryValueName | string | Name of the registry value that the recorded action was applied to. |
| RegistryValueType | string | Data type, such as binary or string, of the registry value that the recorded action was applied to. |
| ReportId | long | Event identifier based on a repeating counter. To identify unique events, this column must be used in conjunction with the ComputerName and EventTime columns.. |
| SourceSystem | string |  |
| TenantId | string |  |
| TimeGenerated | datetime | Date and time when the record was generated. |
| Type | string | The name of the table |
