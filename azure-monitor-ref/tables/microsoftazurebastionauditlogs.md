---
title: Azure Monitor Logs reference - MicrosoftAzureBastionAuditLogs
description: Reference for MicrosoftAzureBastionAuditLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# MicrosoftAzureBastionAuditLogs

 Microsoft Azure Bastion Audit Logs

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Bastions




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ClientIpAddress | string | Browser IP Address that was used to log into the VirtualMachine from Bastion |
| ClientPort | int | Browser Port Number that was used to log into the VirtualMachine from Bastion |
| Duration | int | Duration in milliseconds where the Bastion Session lasted (available only when the Bastion Session ended) |
| Location | string | The location of the server that processed the request (e.g., South Central US). |
| Message | string | Additonal text that's assoicated of this event |
| OperationName | string | The name of the operation represented by this event |
| Protocol | string | Protocol (could be ssh or rdp) that was used to log into the VirtualMachine from Bastion |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SessionEndTime | string | Timestamp (UTC) of when the Bastion Session was ended |
| SessionStartTime | datetime | Timestamp (UTC) of when the Bastion Session was started |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TargetResourceId | string | ResourceID of the VirtualMachine where the Bastion was connected to |
| TargetVMIPAddress | string | IP Address of VirtualMachine where the Bastion was connected to |
| TenantId | string |  |
| Time | datetime | The timestamp (UTC) of the log |
| TimeGenerated | datetime |  |
| TunnelId | string | Internal Bastion Connection GUID |
| Type | string | The name of the table |
| UserAgent | string | Browser User Agent that the request was sent |
| UserEmail | string | UserEmail account that was used to log into the VirtualMachine |
| UserName | string | UserName that was used to log into the VirtualMachine from Bastion |
