---
title: Azure Monitor Logs reference - WaaSDeploymentStatus
description: Reference for WaaSDeploymentStatus table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# WaaSDeploymentStatus

 

## Categories

- Desktop Analytics
## Solutions

- Update Compliance




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Computer | string |  |
| ComputerID | string |  |
| DeferralDays | int |  |
| DeploymentError | string |  |
| DeploymentErrorCode | string |  |
| DeploymentStatus | string |  |
| DetailedStatus | string |  |
| ExpectedInstallDate | datetime |  |
| LastScan | datetime |  |
| OriginBuild | string |  |
| OSBuild | string |  |
| OSRevisionNumber | int |  |
| OSServicingBranch | string |  |
| OSVersion | string |  |
| PauseState | string |  |
| RecommendedAction | string |  |
| ReleaseName | string |  |
| SourceSystem | string |  |
| TargetBuild | string |  |
| TargetOSRevision | int |  |
| TargetOSVersion | string |  |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
| UpdateCategory | string |  |
| UpdateClassification | string |  |
| UpdateReleasedDate | datetime |  |
