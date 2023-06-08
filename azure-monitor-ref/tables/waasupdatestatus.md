---
title: Azure Monitor Logs reference - WaaSUpdateStatus
description: Reference for WaaSUpdateStatus table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
---

# WaaSUpdateStatus

 

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
| DownloadMode | string |  |
| FeatureDeferralDays | int |  |
| FeaturePauseDays | int |  |
| FeaturePauseState | string |  |
| _IsBillable | string |  |
| LastScan | datetime |  |
| NeedAttentionStatus | string |  |
| OSArchitecture | string |  |
| OSBuild | string |  |
| OSCurrentStatus | string |  |
| OSEdition | string |  |
| OSFamily | string |  |
| OSFeatureUpdateStatus | string |  |
| OSName | string |  |
| OSQualityUpdateStatus | string |  |
| OSRevisionNumber | int |  |
| OSSecurityUpdateStatus | string |  |
| OSServicingBranch | string |  |
| OSVersion | string |  |
| QualityDeferralDays | int |  |
| QualityPauseDays | int |  |
| QualityPauseState | string |  |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
