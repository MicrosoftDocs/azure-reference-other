---
title: Azure Monitor Logs reference - MADeviceReadiness
description: Reference for MADeviceReadiness table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 08/09/2023
---

# MADeviceReadiness



## Categories

- Desktop Analytics
## Solutions

- Microsoft365Analytics




## Columns

| Column | Type | Description |
|---|---|---|
| AppIssues | int |   |
| _BilledSize | real | The record size in bytes |
| ConfigMgrClientID | string |   |
| DeploymentPlanId | string |   |
| DeviceId | string |   |
| DeviceLastSeenDate | datetime |   |
| DeviceName | string |   |
| DeviceStatus | int |   |
| DriverIssues | int |   |
| InventoryCompleteness | bool |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| MacroIssues | int |   |
| Manufacturer | string |   |
| ModelFamily | string |   |
| OfficeAddInIssues | int |   |
| OfficeAppIssues | int |   |
| OfficeBuild | string |   |
| OfficeUpgradeDecision | string |   |
| OfficeVersion | string |   |
| OSBuild | string |   |
| OSVersion | string |   |
| PilotDevice | bool |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| SysReqIssues | int |   |
| TimeGenerated | datetime |   |
| TotalIssues | int |   |
| Type | string | The name of the table |
| WindowsUpgradeDecision | string |   |
