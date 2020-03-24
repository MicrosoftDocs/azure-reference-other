---
title: Azure Monitor Logs reference - ConfigurationData
description: Reference for ConfigurationData table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# ConfigurationData

 View the last reported state for in-guest configuration data such as Files Software Registry Keys Windows Services and Linux Daemons

## Categories

- IT & Management Tools
## Solutions

- Change Tracking
## Resource types

- Virtual machine
- Virtual machine scale set




## Columns

|Column|Type|Description|
|---|---|---|
|Computer|string||
|ConfigDataType|string|Type of configuration item: Files Software WindowsServices Registry Daemons|
|SourceComputerId|string||
|SvcDisplayName|string|Human-frinedly name for the service|
|SvcName|string|Name of the service|
|SvcState|string|Current state of the service|
|SvcStartupType|string|Startup behavior of the service|
|SvcAccount|string|User account that is associated with the service executable explicitly to provide a security context for the service|
|SvcRunlevels|string|Modes used by the daemon for system operation|
|SvcController|string|Service property that was changed|
|SvcPath|string|The file path to the executable for the service|
|SvcDescription|string|Parent process for the daemon|
|SourceSystem|string||
|ManagementGroupName|string||
|TimeGenerated|datetime|Date and time the record was created.|
|VMUUID|string||
|SoftwareType|string|Type of the software: Application Package Update|
|SoftwareName|string|Name of the software|
|Publisher|string|Software publisher name|
|CurrentVersion|string|Current software version|
|Architecture|string|Instruction set architecture for the software being tracked|
|Location|string||
|SoftwareDescription|string|Description of the software|
|Name|string||
|FileSystemPath|string|File system path for the reporting file|
|Size|long|Size of the file|
|DateCreated|datetime|Created date of the file|
|DateModified|datetime|Last modified date of the file|
|Attributes|string||
|Acls|string|The Access-Control List specifies which users or system processes are granted access to objects|
|FileContentChecksum|string|Checksum of the reporting file|
|RegistryKey|string|Registy key name|
|Hive|string|Registry hive for the reporting registry key|
|ValueName|string|Name of the value for the registry key being tracked|
|ValueData|string|Data contained in the value and registry key being tracked|
|ValueType|string|Type of the value for the registry key being tracked|
|Type|string||
|_ResourceId|string||
