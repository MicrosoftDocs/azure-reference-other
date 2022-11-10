---
title: Azure Monitor Logs reference - DeviceProcessEvents
description: Reference for DeviceProcessEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# DeviceProcessEvents

 This table is part of Microsoft Defender for Endpoints with Azure Sentinel. This table contains Process creation and related events.

## Categories

- Security
## Solutions

- Microsoft Sentinel




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AccountDomain | string | Domain of the account. |
| AccountName | string | User name of the account. |
| AccountObjectId | string | Unique identifier for the account in Azure AD. |
| AccountSid | string | Security Identifier (SID) of the account. |
| AccountUpn | string | User principal name (UPN) of the account. |
| ActionType | string | Type of activity that triggered the event. |
| AdditionalFields | dynamic | Additional information about the entity or event. |
| AppGuardContainerId | string | Identifier for the virtualized container used by Application Guard to isolate browser activity. |
| DeviceId | string | Unique identifier for the device in the service. |
| DeviceName | string | Fully qualified domain name (FQDN) of the device. |
| FileName | string | Name of the file that the recorded action was applied to. |
| FolderPath | string | Folder containing the file that the recorded action was applied to. |
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
| InitiatingProcessLogonId | long | Identifier for a logon session of the process that initiated the event. This identifier is unique on the same machine only between restarts.. |
| InitiatingProcessMD5 | string | MD5 hash of the process (image file) that initiated the event. |
| InitiatingProcessParentCreationTime | datetime | Date and time when the parent of the process responsible for the event was started. |
| InitiatingProcessParentFileName | string | Name of the parent process that spawned the process responsible for the event. |
| InitiatingProcessParentId | long | Process ID (PID) of the parent process that spawned the process responsible for the event. |
| InitiatingProcessSHA1 | string | SHA-1 hash of the process (image file) that initiated the event. |
| InitiatingProcessSHA256 | string | SHA-256 hash of the process (image file) that initiated the event. This field is usually not populated - use the SHA1 column when available.. |
| InitiatingProcessTokenElevation | string | Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event. |
| LogonId | long | Identifier for a logon session. This identifier is unique on the same machine only between restarts. |
| MachineGroup | string | Machine group of the machine. This group is used by role-based access control to determine access to the machine. |
| MD5 | string | MD5 hash of the file that the recorded action was applied to. |
| ProcessCommandLine | string | Command line used to create the new process. |
| ProcessCreationTime | datetime | Date and time the process was created. |
| ProcessId | long | Process ID (PID) of the newly created process. |
| ProcessIntegrityLevel | string | Integrity level of the newly created process. Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet downloaded. These integrity levels influence permissions to resources.. |
| ProcessTokenElevation | string | Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the newly created process. |
| ReportId | long | Event identifier based on a repeating counter. To identify unique events, this column must be used in conjunction with the ComputerName and EventTime columns.. |
| SHA1 | string | SHA-1 hash of the file that the recorded action was applied to. |
| SHA256 | string | SHA-256 of the file that the recorded action was applied to. |
| SourceSystem | string |  |
| TenantId | string |  |
| TimeGenerated | datetime | Date and time when the record was generated. |
| Type | string | The name of the table |
