---
title: Azure Monitor Logs reference - MAApplicationReadiness
description: Reference for MAApplicationReadiness table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 08/09/2023
---

# MAApplicationReadiness



## Categories

- Desktop Analytics
## Solutions

- Microsoft365Analytics




## Columns

| Column | Type | Description |
|---|---|---|
| AdoptionStatus | string |   |
| AHAInsight | string |   |
| AppCategory | string |   |
| AppLanguage | string |   |
| AppName | string |   |
| AppType | string |   |
| AppVendor | string |   |
| AppVersion | string |   |
| _BilledSize | real | The record size in bytes |
| DeploymentPlanId | string |   |
| DevicesWithIssues | int |   |
| Guidance | string |   |
| HasSupportStatement | bool |   |
| Importance | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Issue | string |   |
| IsVirtualized | bool |   |
| MonthlyActiveDevices | int |   |
| Notes | string |   |
| NPId | string |   |
| ProgramId | string |   |
| Remediation | string |   |
| RiskAssessment | string |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| TestOwner | string |   |
| TestPlan | string |   |
| TestResult | string |   |
| TimeGenerated | datetime |   |
| TotalInstalls | int |   |
| Type | string | The name of the table |
| UpgradeDecision | string |   |
