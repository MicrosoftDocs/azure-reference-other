---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: MDCFileIntegrityMonitoringEvents
---


| Column | Type | Description |
|---|---|---|
| AADTenantID | string | The AAD tenant Id of the subscription in which the monitored entity was created, renamed, modified or deleted. |
| _BilledSize | real | The record size in bytes |
| ChangeType | string | The type of change that occurred on the entity. For 'File' entity must be either 'Created', 'Modified', 'Renamed' or 'Deleted'. For 'Registry' entity must be either 'RegistryKeyCreated', 'RegistryKeyDeleted', 'RegistryValueSet',  'RegistryValueDeleted', 'RegistryKeyRenamed'. |
| CloudIdentifier | string | The cloud identifier of the resource. |
| CloudProvider | string | The cloud provider of the resource. |
| CloudResourceType | string | The type of the cloud resource. |
| Computer | string | The name of the machine on which the monitored entity was created, renamed, modified or deleted. |
| FileMd5 | string | Relevant for 'File' monitored entity type. Holds the MD5 of the file that was modified, created or deleted. |
| FileName | string | Relevant for 'File' monitored entity type. Holds the name of the file that was created, renamed, modified or deleted. |
| FilePath | string | Relevant for 'File' monitored entity type. Holds the path of the file that was created, renamed, modified or deleted. |
| FileSha1 | string | Relevant for 'File' monitored entity type. Holds the SHA1 of the file that was modified, created or deleted. |
| FileSha256 | string | Relevant for 'File' monitored entity type. Holds the SHA256 of the file that was modified, created or deleted. |
| FileSize | long | Relevant for 'File' monitored entity type. Holds the current size (in bytes) of the file that was created, renamed, modified or deleted. |
| FileType | string | Relevant for 'File' monitored entity type. Holds the type of the file that was created, renamed, modified or deleted. Example of possible values: Zip, PDF, Xar etc. |
| InitiatingProcessAccountDomainName | string | Holds the account domain name of the initiating process that caused the monitored entity event. |
| InitiatingProcessAccountName | string | Holds the account name of the initiating process that caused the monitored entity event. |
| InitiatingProcessAccountSid | string | Holds the account SID of the initiating process that caused the monitored entity event. |
| InitiatingProcessCreationTime | datetime | Holds the creation time of the initiating process that caused the monitored entity event. |
| InitiatingProcessFirstSeen | datetime | Holds the first seen time of the initiating process that caused the monitored entity event. |
| InitiatingProcessId | long | Holds the process Id of the initiating process that caused the monitored entity event. |
| InitiatingProcessImageFileName | string | Holds the image file name of the initiating process that caused the monitored entity event. |
| InitiatingProcessImageFilePath | string | Holds the image file path of the initiating process that caused the monitored entity event. |
| InitiatingProcessImageFileType | string | Holds the image file type of the initiating process that caused the monitored entity event. |
| InitiatingProcessName | string | Holds the name of the initiating process that caused the monitored entity event. |
| InitiatingProcessSessionId | long | Holds the session Id of the initiating process that caused the monitored entity event. |
| InitiatingProcessSource | string | Holds the source of the initiating process that caused the monitored entity event. |
| InitProcImageCreationTimeUtc | datetime | Holds the image creation time for the image of the initiating process that caused the monitored entity event. |
| InitProcImageFileSizeInBytes | long | Holds the image file size (in Bytes) of the initiating process that caused the monitored entity event. |
| InitProcImageLastAccessTimeUtc | datetime | Holds the image last access time for the image of the initiating process that caused the monitored entity event. |
| InitProcImageLastWriteTimeUtc | datetime | Holds the image last write time for the image of the initiating process that caused the monitored entity event. |
| InitProcImageLsHash | string | Holds the image LS hash for the image of the initiating process that caused the monitored entity event. |
| InitProcImageMd5 | string | Holds the image MD5 for the image of the initiating process that caused the monitored entity event. |
| InitProcImagePeTimestampUtc | datetime | Holds the image PE time for the image of the initiating process that caused the monitored entity event. |
| InitProcImageSha1 | string | Holds the image SHA 1 for the image of the initiating process that caused the monitored entity event. |
| InitProcImageSha256 | string | Holds the image SHA 256 for the image of the initiating process that caused the monitored entity event. |
| InitProcVersionInfoCompanyName | string | Holds the version info company name of the initiating process that caused the monitored entity event. |
| InitProcVersionInfoFileDescription | string | Holds the version info file description of the initiating process that caused the monitored entity event. |
| InitProcVersionInfoInternalFileName | string | Holds the version info internal file name of the initiating process that caused the monitored entity event. |
| InitProcVersionInfoOriginalFileName | string | Holds the version info original file name of the initiating process that caused the monitored entity event. |
| InitProcVersionInfoProductName | string | Holds the version info product name of the initiating process that caused the monitored entity event. |
| InitProcVersionInfoProductVersion | string | Holds the version info product version of the initiating process that caused the monitored entity event. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| MonitoredEntityType | string | The type of the monitored entity that was created, renamed, modified or deleted. Can be either 'File' or 'Registry'. |
| NewValueData | string | Relevant for 'Registry' monitored entity type. Holds the New registry value data. |
| NewValueName | string | Relevant for 'Registry' monitored entity type. Holds the New registry value name. |
| NewValueType | string | Relevant for 'Registry' monitored entity type. Holds the New registry value type. |
| OldValueData | string | Relevant for 'Registry' monitored entity type. Holds the previous registry value data. |
| OldValueFullRegistryKey | string | Relevant for 'Registry' monitored entity type. Holds the previous full registry key. |
| OldValueName | string | Relevant for 'Registry' monitored entity type. Holds the previous registry value name. |
| OldValueType | string | Relevant for 'Registry' monitored entity type. Holds the previous registry value type. |
| OriginalFileName | string | Relevant for 'File' monitored entity type and for a 'Rename' change type. Holds the original name the file that was renamed, before the  rename occured. |
| OriginalFilePath | string | Relevant for 'File' monitored entity type and for a 'Rename' change type. Holds the original path of the file that was renamed, before the  rename occured. |
| RegistryHive | string | Relevant for 'Registry' monitored entity type. Holds the grouping configuration settings for the operating system and applications. |
| RegistryKey | string | Relevant for 'Registry' monitored entity type. Holds the full registry key of the registry that was created or the new registry key of the registry that was renamed. |
| RequestAccountDomain | string | Relevant for 'File' monitored entity type. Holds the domain of the account of the user that caused the file event. |
| RequestAccountName | string | Relevant for 'File' monitored entity type. Holds the name of the account of the user that caused the file event. |
| RequestAccountSid | string | Relevant for 'File' monitored entity type. Holds the SID of the account of the user that caused the file event. |
| RequestSource | string | Relevant for 'File' monitored entity type. Holds the source of the account of the user that caused the file event. For example Local/SMB/NFS. |
| RequestSourceIP | string | Relevant for 'File' monitored entity type. Holds the source IP of the account of the user that caused the file event. For remote file, the IP from which the request came. |
| RequestSourcePort | string | Relevant for 'File' monitored entity type. Holds the source port of the account of the user that caused the file event. For remote file, the port from which the request came. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The time (UTC) when the monitored entity was created, renamed, modified or deleted. |
| Type | string | The name of the table |
