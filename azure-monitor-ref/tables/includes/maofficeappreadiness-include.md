---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: MAOfficeAppReadiness
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| DeploymentPlanId | string |   |
| DevicesWithIssues | int |   |
| Guidance | string |   |
| Importance | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Issue | string |   |
| MonthlyActiveUsers | int |   |
| Notes | string |   |
| OfficeAppArchitecture | string |   |
| OfficeAppId | string |   |
| OfficeAppMajorVersion | int |   |
| OfficeAppName | string |   |
| OfficeAppRelease | string |   |
| OfficeAppVersion | string |   |
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
