---
title: Azure Monitor Logs reference - MAWindowsDeploymentStatus
description: Reference for MAWindowsDeploymentStatus table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 08/09/2023
---

# MAWindowsDeploymentStatus



## Categories

- Desktop Analytics
## Solutions

- Microsoft365Analytics




## Columns

| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| BuildId | int |   |
| DeploymentDuration | int |   |
| DeploymentEndTime | datetime |   |
| DeploymentOverviewStatus | string |   |
| DeploymentStage | string |   |
| DeploymentStartTime | datetime |   |
| DeploymentStatus | string |   |
| DeviceId | string |   |
| DeviceName | string |   |
| ErrorCode | int |   |
| ErrorDescription | string |   |
| ExtendedErrorCode | int |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| LastEventTime | datetime |   |
| Manufacturer | string |   |
| Model | string |   |
| PauseState | string |   |
| RecommendedAction | string |   |
| ReleaseType | string |   |
| ReleaseVersion | string |   |
| SourceBuild | string |   |
| StateName | string |   |
| TargetBuild | string |   |
| TargetReleaseName | string |   |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
| UpdateDeferral | int |   |
| UpdateSource | string |   |
