---
title: Azure Monitor Logs reference - UpdateSummary
description: Reference for UpdateSummary table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
---

# UpdateSummary

 Summary for each update schedule run. Includes information such as how many updates were not installed.

## Categories

- Virtual Machines
## Solutions

- Security and Audit
- SecurityCenter
- SecurityCenterFree
- Update Management
## Resource types

- Virtual machines
- VMware
- Azure Stack HCI
- System Center Virtual Machine Manager
- Virtual Machine Scale Sets
- Automation account




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Computer | string |  |
| ComputerEnvironment | string |  |
| CriticalUpdatesMissing | int |  |
| ManagementGroupName | string |  |
| NETRuntimeVersion | string |  |
| OldestMissingSecurityUpdateBucket | string |  |
| OldestMissingSecurityUpdateInDays | int |  |
| OsVersion | string |  |
| OtherUpdatesMissing | int |  |
| Resource | string |  |
| ResourceGroup | string |  |
| ResourceId | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResourceProvider | string |  |
| ResourceType | string |  |
| RestartPending | bool |  |
| SecurityUpdatesMissing | int |  |
| SourceComputerId | string |  |
| SourceSystem | string |  |
| SubscriptionId | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime |  |
| TotalUpdatesMissing | int |  |
| Type | string | The name of the table |
| VMUUID | string |  |
| WindowsUpdateAgentVersion | string |  |
| WindowsUpdateSetting | string |  |
| WSUSServer | string |  |
