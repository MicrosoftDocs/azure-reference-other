---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: MADriverReadiness
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| DeploymentPlanId | string |   |
| DriverAvailability | string |   |
| DriverDate | string |   |
| DriverKey | long |   |
| DriverName | string |   |
| DriverVendor | string |   |
| DriverVersion | string |   |
| Guidance | string |   |
| HardwareID | string |   |
| HardwareName | string |   |
| HardwareType | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Issue | string |   |
| Remediation | string |   |
| RiskAssessment | string |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| TimeGenerated | datetime |   |
| TotalComputers | int |   |
| Type | string | The name of the table |
| UpgradeDecision | string |   |
