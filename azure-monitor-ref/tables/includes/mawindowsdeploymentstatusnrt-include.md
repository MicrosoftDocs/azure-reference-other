---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: MAWindowsDeploymentStatusNRT
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| DeploymentStage | string |   |
| DeviceId | string |   |
| DeviceName | string |   |
| ErrorCode | int |   |
| ErrorDescription | string |   |
| ErrorFriendlyName | string |   |
| ExtendedErrorCode | int |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Manufacturer | string |   |
| Model | string |   |
| RecommendedAction | string |   |
| SourceBuild | string |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| SourceVersion | string |   |
| TargetBuild | string |   |
| TargetVersion | string |   |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
| UpdateSource | string |   |
