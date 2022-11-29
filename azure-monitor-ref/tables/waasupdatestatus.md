---
title: Azure Monitor Logs reference - WaaSUpdateStatus
description: Reference for WaaSUpdateStatus table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# WaaSUpdateStatus

 

## Categories

- Desktop Analytics
## Solutions

- Update Compliance




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Computer | string |  |
| ComputerID | string |  |
| DownloadMode | string |  |
| FeatureDeferralDays | int |  |
| FeaturePauseDays | int |  |
| FeaturePauseState | string |  |
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
| SourceSystem | string |  |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
