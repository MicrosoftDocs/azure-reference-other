---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: MAOfficeAddinReadiness
---


| Column | Type | Description |
|---|---|---|
| AddinInstanceId | string |   |
| AddinName | string |   |
| AddinProducts | string |   |
| AddinPublisher | string |   |
| AddinRemarks | string |   |
| AddinSupportStatementUrl | string |   |
| AddinSupportStatus | string |   |
| AddinVersion | string |   |
| AdoptionStatus | string |   |
| _BilledSize | real | The record size in bytes |
| DeploymentPlanId | string |   |
| Guidance | string |   |
| Importance | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Issue | string |   |
| Remediation | string |   |
| RiskAssessment | string |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| TargetOfficeBitness | string |   |
| TestOwner | string |   |
| TestPlan | string |   |
| TestResult | string |   |
| TimeGenerated | datetime |   |
| TotalInstalls | int |   |
| Type | string | The name of the table |
| UpgradeDecision | string |   |
