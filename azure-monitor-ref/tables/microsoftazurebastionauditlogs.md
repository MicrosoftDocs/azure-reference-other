---
title: Azure Monitor Logs reference - MicrosoftAzureBastionAuditLogs
description: Reference for MicrosoftAzureBastionAuditLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# MicrosoftAzureBastionAuditLogs

 Microsoft Azure Bastion Audit Logs

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Bastion




## Columns

|Column|Type|Description|
|---|---|---|
|TenantId|string||
|SourceSystem|string||
|TimeGenerated|datetime||
|Time|datetime|The timestamp (UTC) of the log|
|OperationName|string|The name of the operation represented by this event|
|Location|string|The location of the server that processed the request (e.g., South Central US).|
|UserAgent|string|Browser User Agent that the request was sent|
|UserName|string|UserName that was used to log into the VirtualMachine from Bastion|
|ClientIpAddress|string|Browser IP Address that was used to log into the VirtualMachine from Bastion|
|ClientPort|int|Browser Port Number that was used to log into the VirtualMachine from Bastion|
|Protocol|string|Protocol (could be ssh or rdp) that was used to log into the VirtualMachine from Bastion|
|TargetResourceId|string|ResourceID of the VirtualMachine where the Bastion was connected to|
|Message|string|Additonal text that's assoicated of this event|
|TargetVMIPAddress|string|IP Address of VirtualMachine where the Bastion was connected to|
|TunnelId|string|Internal Bastion Connection GUID|
|SessionStartTime|datetime|Timestamp (UTC) of when the Bastion Session was started|
|SessionEndTime|string|Timestamp (UTC) of when the Bastion Session was ended|
|Duration|int|Duration in milliseconds where the Bastion Session lasted (available only when the Bastion Session ended)|
|Type|string||
|_ResourceId|string||
