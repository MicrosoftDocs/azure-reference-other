---
title: Azure Monitor Logs reference - DynamicEventCollection
description: Reference for DynamicEventCollection table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# DynamicEventCollection

 A generic windows events table for data collected by the Defender for Endpoint agent

## Categories

- Security
## Solutions

- AzureSentinelDSRE




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AccountSid | string | Security identifier (SID) of the account. |
| AdditionalFields | dynamic | Additional information about the entity or event. |
| AppGuardContainerId | string | Identifier for the virtualized container used by Application Guard to isolate browser activity. |
| DeviceId | string | Unique identifier for the device in the service. |
| DeviceName | string | Fully qualified domain name (FQDN) of the device. |
| EventId | long | Contains the unique event identifier. |
| InitiatingProcessAccountDomain | string | Domain of the account that ran the process responsible for the event. |
| InitiatingProcessAccountName | string | User name of the account that ran the process responsible for the event. |
| InitiatingProcessAccountObjectId | string | Azure AD object ID of the user account that ran the process responsible for the event. |
| InitiatingProcessAccountSid | string | Security Identifier (SID) of the account that ran the process responsible for the event. |
| InitiatingProcessAccountUpn | string | User principal name (UPN) of the account that ran the process responsible for the event. In Active Directory, a UPN is the name of a system user in an email address format (for example: john.doe@domain.com) |
| InitiatingProcessFolderPath | string | Folder containing the process (image file) that initiated the event. |
| InitiatingProcessId | long | Process ID (PID) of the process that initiated the event. |
| InitiatingProcessLogonId | long | Identifier for a logon session of the process that initiated the event. This identifier is unique on the same machine only between restarts. |
| InitiatingProcessMD5 | string | MD5 hash of the process (image file) that initiated the event. |
| InitiatingProcessParentFileName | string | Name of the parent process that spawned the process responsible for the event. |
| InitiatingProcessParentId | long | Process ID (PID) of the parent process that spawned the process responsible for the event. |
| InitiatingProcessSHA1 | string | SHA-1 hash of the process (image file) that initiated the event. |
| LocalIP | string | IP address assigned to the local machine used during communication. |
| LocalPort | int | TCP port on the local machine used during communication. |
| MachineGroup | string | Machine group of the machine. This group is used by role-based access control to determine access to the machine. |
| ProcessCommandLine | string | Command line used to create the new process. |
| RemoteDeviceName | string | Name of the device that performed a remote operation on the affected machine. Depending on the event being reported, this name could be a fully-qualified domain name (FQDN), a NetBIOS name, or a host name without domain information.. |
| RemoteIP | string | IP address that was being connected to. |
| RemotePort | int | TCP port on the remote device that was being connected to. |
| ReportId | long | Unique identifier for the event. |
| SourceSystem | string |  |
| TenantId | string |  |
| TimeGenerated | datetime | Date and time (UTC) when the record was generated. |
| Type | string | The name of the table |
