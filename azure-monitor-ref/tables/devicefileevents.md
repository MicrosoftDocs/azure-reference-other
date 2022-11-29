---
title: Azure Monitor Logs reference - DeviceFileEvents
description: Reference for DeviceFileEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# DeviceFileEvents

 This table is part of Microsoft Defender for Endpoints with Azure Sentinel. This table contains File creation, modification, and other file system events.

## Categories

- Security
## Solutions

- Microsoft Sentinel




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ActionType | string | Type of activity that triggered the event. |
| AdditionalFields | dynamic | Additional information about the entity or event. |
| AppGuardContainerId | string | Identifier for the virtualized container used by Application Guard to isolate browser activity. |
| DeviceId | string | Unique identifier for the device in the service. |
| DeviceName | string | Fully qualified domain name (FQDN) of the device. |
| FileName | string | Name of the file that the recorded action was applied to. |
| FileOriginIP | string | IP address where the file was downloaded from. |
| FileOriginReferrerUrl | string | URL of the web page that links to the downloaded file. |
| FileOriginUrl | string | URL where the file was downloaded from. |
| FileSize | long | Size of the file in bytes. |
| FolderPath | string | Folder containing the file that the recorded action was applied to. |
| InitiatingProcessAccountDomain | string | Domain of the account that ran the process responsible for the event. |
| InitiatingProcessAccountName | string | User name of the account that ran the process responsible for the event. |
| InitiatingProcessAccountObjectId | string | Azure AD object ID of the user account that ran the process responsible for the event. |
| InitiatingProcessAccountSid | string | Security Identifier (SID) of the account that ran the process responsible for the event. |
| InitiatingProcessAccountUpn | string | User principal name (UPN) of the account that ran the process responsible for the event. |
| InitiatingProcessCommandLine | string | Command line used to run the process that initiated the event. |
| InitiatingProcessCreationTime | datetime | Date and time when the parent of the process responsible for the event was started. |
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
| IsAzureInfoProtectionApplied | bool | Indicates whether the file is encrypted by Azure Information Protection. |
| MachineGroup | string | Machine group of the machine. This group is used by role-based access control to determine access to the machine. |
| MD5 | string | MD5 hash of the file that the recorded action was applied to. |
| PreviousFileName | string | Original name of the file that was renamed as a result of the action. |
| PreviousFolderPath | string | Original folder containing the file before the recorded action was applied. |
| ReportId | long | Event identifier based on a repeating counter. To identify unique events, this column must be used in conjunction with the ComputerName and EventTime columns.. |
| RequestAccountDomain | string | Domain of the account used to remotely initiate the activity. |
| RequestAccountName | string | User name of account used to remotely initiate the activity. |
| RequestAccountSid | string | Security Identifier (SID) of the account used to remotely initiate the activity. |
| RequestProtocol | string | Network protocol, if applicable, used to initiate the activity: Unknown, Local, SMB, or NFS. |
| RequestSourceIP | string | IPv4 or IPv6 address of the remote device that initiated the activity. |
| RequestSourcePort | int | Source port on the remote device that initiated the activity. |
| SensitivityLabel | string | Label applied to an email, file, or other content to classify it for information protection. |
| SensitivitySubLabel | string | Sublabel applied to an email, file, or other content to classify it for information protection; sensitivity sublabels are grouped under sensitivity labels but are treated independently. |
| SHA1 | string | SHA-1 hash of the file that the recorded action was applied to. |
| SHA256 | string | SHA-256 of the file that the recorded action was applied to. |
| ShareName | string | Name of shared folder containing the file. |
| SourceSystem | string |  |
| TenantId | string |  |
| TimeGenerated | datetime | Date and time when the record was generated. |
| Type | string | The name of the table |
