---
title: Azure Monitor Logs reference - UAApp
description: Reference for UAApp table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
---

# UAApp

 

## Categories

- Desktop Analytics
## Solutions

- Upgrade Readiness




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AppCategory | string |  |
| AppLanguage | string |  |
| AppName | string |  |
| AppOwner | string |  |
| AppType | string |  |
| AppVendor | string |  |
| AppVersion | string |  |
| _BilledSize | real |  |
| Computer | string |  |
| ComputerID | string |  |
| ComputersWithIssues | int |  |
| Guidance | string |  |
| Importance | string |  |
| _IsBillable | string |  |
| IsRollup | bool |  |
| Issue | string |  |
| MonthlyActiveComputers | int |  |
| PercentActiveComputers | string |  |
| ReadyForWindows | string |  |
| RollupLevel | string |  |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| TestPlan | string |  |
| TestResult | string |  |
| TimeGenerated | datetime |  |
| TotalInstalls | int |  |
| Type | string | The name of the table |
| UpgradeAssessment | string |  |
| UpgradeDecision | string |  |
