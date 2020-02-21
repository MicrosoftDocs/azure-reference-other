---
title: Azure Monitor Logs reference - ConfigurationChange
description: Reference for ConfigurationChange table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 2/20/2020
---

# ConfigurationChange

 View changes to in-guest configuration data such as Files Software Registry Keys Windows Services and Linux Daemons

## Columns

|Column|Type|Description|
|---|---|---|
|Computer|string||
|ConfigChangeType|string|Type of configuration item that changed: Files Software WindowsServices Registry Daemons|
|ChangeCategory|string|The type of change that occurred: Added Removed Modified|
|SourceComputerId|string||
|SoftwareType|string|Type of the software: Application Package Update|
|SoftwareName|string|Name of the software|
|Previous|string|Previous value|
|Current|string|Current value|
|Publisher|string|Software publisher name|
|Location|string||
|SoftwareDescription|string|Description of the software|
|SvcChangeType|string|Service property that was changed|
|SvcDisplayName|string|Human-frinedly name for the service|
|SvcName|string|Name of the service|
|SvcState|string|Current state of the service|
|SvcPreviousState|string|Previous state of the service|
|SvcStartupType|string|Startup behavior of the service|
|SvcPreviousStartupType|string|Previous startup behavior of the service|
|SvcAccount|string|User account that is associated with the service executable explicitly to provide a security context for the service|
|SvcPreviousAccount|string|Previous user account that was associated with the sevice executable|
|SvcRunlevels|string|Modes used by the daemon for system operation|
|SvcPreviousRunlevels|string|Previous modes used by the daemon for system operation|
|SvcController|string|Parent process for the daemon|
|SvcPreviousController|string|Previous parent process for the daemon|
|SvcPath|string|The file path to the executable for the service|
|SvcPreviousPath|string|Previous file path to the executable for the service|
|RegistryKey|string|Registry key name|
|Hive|string|Registry hive for the changed registry key|
|ValueName|string|Name of the value for the registry key being tracked|
|ValueData|string|Data contained in the value and registry key being tracked|
|PreviousValueData|string|Previous registry value data|
|ValueType|string|Type of the value for the registry key being tracked|
|PreviousValueType|string|Previous registry value type|
|Name|string||
|FileSystemPath|string|File system path for the changed file|
|Size|long|Current size of the changed file|
|PreviousSize|long|Previous file size|
|DateCreated|datetime|Date that the item was created|
|PreviousDateCreated|datetime|Previous date created time|
|DateModified|datetime|Date that the item was last modified|
|PreviousDateModified|datetime|Previous date modified time|
|Attributes|string||
|PreviousAttributes|string|Previous attributes value|
|Acls|string|The Access-Control List specifies which users or system processes are granted access to objects|
|PreviousAcls|string|Previous Acl value|
|FieldsChanged|string|Fields that were changed as part of the change record|
|FileContentChecksum|string|Checksum of the file content|
|PreviousFileContentChecksum|string|Previous file content checksum value|
|SourceSystem|string||
|ManagementGroupName|string|Name of a resource's assigned management group|
|TimeGenerated|datetime|Date and time the record was created.|
|VMUUID|string||
|LastSnapshotAge|long|Age of the last snapshot|
|Type|string||
|_ResourceId|string||
