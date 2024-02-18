---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: UAUpgradedComputer
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Computer | string |   |
| ComputerID | string |   |
| ConfigMgrClientID | string |   |
| DeploymentError | string |   |
| DeploymentErrorDetails | string |   |
| DeploymentStatus | string |   |
| HoursToUninstall | int |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| LastScan | datetime |   |
| Manufacturer | string |   |
| Model | string |   |
| OriginBuild | string |   |
| OriginOSVersion | string |   |
| OSArchitecture | string |   |
| OSBuild | string |   |
| OSEdition | string |   |
| OSVersion | string |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| TargetBuild | string |   |
| TargetOSVersion | string |   |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
| UninstallComment | string |   |
| UninstallReason | string |   |
| UserAction | string |   |
