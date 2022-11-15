---
title: Azure Monitor Logs reference - UpdateRunProgress
description: Reference for UpdateRunProgress table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# UpdateRunProgress

 Breaks down each run of your update schedule by the patches available at the time with details on the installation status of each patch.

## Categories

- IT & Management Tools
## Solutions

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
| CorrelationId | string |  |
| EndTime | datetime |  |
| ErrorResult | string |  |
| InstallationStatus | string |  |
| KBID | string |  |
| ManagementGroupName | string |  |
| OSType | string |  |
| Product | string |  |
| Resource | string |  |
| ResourceGroup | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResourceId | string |  |
| ResourceProvider | string |  |
| ResourceType | string |  |
| SourceComputerId | string |  |
| SourceSystem | string |  |
| StartTime | datetime |  |
| SubscriptionId | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| SucceededOnRetry | bool |  |
| TimeGenerated | datetime |  |
| Title | string |  |
| Type | string | The name of the table |
| UpdateId | string |  |
| UpdateRunName | string |  |
| VMUUID | string |  |
