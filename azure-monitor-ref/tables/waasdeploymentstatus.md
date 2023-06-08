---
title: Azure Monitor Logs reference - WaaSDeploymentStatus
description: Reference for WaaSDeploymentStatus table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
---

# WaaSDeploymentStatus

 

## Categories

- Desktop Analytics
## Solutions

- Update Compliance




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real |  |
| Computer | string |  |
| ComputerID | string |  |
| DeferralDays | int |  |
| DeploymentError | string |  |
| DeploymentErrorCode | string |  |
| DeploymentStatus | string |  |
| DetailedStatus | string |  |
| ExpectedInstallDate | datetime |  |
| _IsBillable | string |  |
| LastScan | datetime |  |
| OriginBuild | string |  |
| OSBuild | string |  |
| OSRevisionNumber | int |  |
| OSServicingBranch | string |  |
| OSVersion | string |  |
| PauseState | string |  |
| RecommendedAction | string |  |
| ReleaseName | string |  |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| TargetBuild | string |  |
| TargetOSRevision | int |  |
| TargetOSVersion | string |  |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
| UpdateCategory | string |  |
| UpdateClassification | string |  |
| UpdateReleasedDate | datetime |  |
