---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: SecurityAttackPathData
---


| Column | Type | Description |
|---|---|---|
| AdditionalRemediationSteps | string | The manual remediation steps of the attack path. |
| Assessments | dynamic | The assessments mapped to the attack path. |
| AttackPathId | string | The ID of the attack path. |
| AttackStory | string | The attack story. |
| _BilledSize | real | The record size in bytes |
| Description | string | The description of the attack path. |
| DisplayName | string | The display name of the attack path. |
| EntrypointId | string | The ID of the attack path enry point. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Mitre | string | MITRE mapping of the path. |
| Path | dynamic | The nodes, edges & insights that create the path. |
| PotentialImpact | string | The potenrial impact of the attack path. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RiskFactors | dynamic | The risk factors of the attack path. |
| RiskLevel | string | The risk level of the attack path. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TargetId | string | The ID of the attack path target. |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The date and time the attack path was exported. |
| Type | string | The name of the table |
