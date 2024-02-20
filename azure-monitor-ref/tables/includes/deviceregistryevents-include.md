---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: DeviceRegistryEvents
---


| Column | Type | Description |
|---|---|---|
| ActionType | string | Type of activity that triggered the event. |
| AppGuardContainerId | string | Identifier for the virtualized container used by Application Guard to isolate browser activity. |
| _BilledSize | real | The record size in bytes |
| DeviceId | string | Unique identifier for the device in the service. |
| DeviceName | string | Fully qualified domain name (FQDN) of the device. |
| InitiatingProcessAccountDomain | string | Domain of the account that ran the initiating process. |
| InitiatingProcessAccountName | string | User name of the account that ran the initiating process. |
| InitiatingProcessAccountObjectId | string | Azure AD object ID of the user account that ran the initiating process. |
| InitiatingProcessAccountSid | string | Security Identifier (SID) of the account that ran the initiating process. |
| InitiatingProcessAccountUpn | string | User principal name (UPN) of the account that ran the initiating process. |
| InitiatingProcessCommandLine | string | Command line used to run the initiating process. |
| InitiatingProcessCreationTime | datetime | Date and time when the process that initiated the event was started. |
| InitiatingProcessFileName | string | Name of the initiating process. |
| InitiatingProcessFileSize | long | The size of the file (bytes) that ran the process responsible for the event. |
| InitiatingProcessFolderPath | string | Folder containing the initiating process (image file). |
| InitiatingProcessId | long | Process ID (PID) of the initiating process. |
| InitiatingProcessIntegrityLevel | string | Integrity level of the initiating process. Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download. These integrity levels influence permissions to resources.. |
| InitiatingProcessMD5 | string | MD5 hash of the initiating process (image file). |
| InitiatingProcessParentCreationTime | datetime | Date and time when the parent of the process responsible for the event was started. |
| InitiatingProcessParentFileName | string | Name of the parent process that spawned the initiating process. |
| InitiatingProcessParentId | long | Process ID (PID) of the parent process that spawned the initiating process. |
| InitiatingProcessSHA1 | string | SHA-1 hash of the initiating process (image file). |
| InitiatingProcessSHA256 | string | SHA-256 hash of the initiating process (image file). In some cases this column may not be populated - please use the InitiatingProcessSHA1 column instead. |
| InitiatingProcessTokenElevation | string | Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the initiating process. |
| InitiatingProcessVersionInfoCompanyName | string | The company name in version information (image file) responsible for the event. |
| InitiatingProcessVersionInfoFileDescription | string | The description in version information (image file) responsible for the event. |
| InitiatingProcessVersionInfoInternalFileName | string | The internal file name in version information (image file) responsible for the event. |
| InitiatingProcessVersionInfoOriginalFileName | string | The original file name in version information (image file) responsible for the event. |
| InitiatingProcessVersionInfoProductName | string | The product name in version information (image file) responsible for the event. |
| InitiatingProcessVersionInfoProductVersion | string | The product version in version information (image file) responsible for the event. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| MachineGroup | string | Machine group of the machine. This group is used by role-based access control to determine access to the machine. |
| PreviousRegistryKey | string | Original registry key before it was modified. |
| PreviousRegistryValueData | string | Original data of the registry value before it was modified. |
| PreviousRegistryValueName | string | Original name of the registry value before it was modified. |
| RegistryKey | string | Registry key that the recorded action was applied to. |
| RegistryValueData | string | Data of the registry value that the recorded action was applied to. |
| RegistryValueName | string | Name of the registry value that the recorded action was applied to. |
| RegistryValueType | string | Data type, such as binary or string, of the registry value that the recorded action was applied to. |
| ReportId | long | Event identifier based on a repeating counter. To identify unique events, this column must be used in conjunction with the ComputerName and EventTime columns.. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Date and time the event was recorded by the MDE agent on the endpoint. |
| Type | string | The name of the table |
