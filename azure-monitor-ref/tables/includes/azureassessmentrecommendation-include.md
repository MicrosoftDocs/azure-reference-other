---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: AzureAssessmentRecommendation
---


| Column | Type | Description |
|---|---|---|
| AADTenantDomain | string |   |
| AADTenantId | string |   |
| AADTenantName | string |   |
| ActionArea | string |   |
| ActionAreaId | string |   |
| AffectedObjectName | string |   |
| AffectedObjectType | string |   |
| AssessmentId | string |   |
| _BilledSize | real | The record size in bytes |
| Computer | string |   |
| CustomData | string |   |
| Description | string |   |
| FocusArea | string |   |
| FocusAreaId | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Recommendation | string |   |
| RecommendationId | string |   |
| RecommendationResult | string |   |
| RecommendationWeight | real |   |
| Resource | string |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| Technology | string |   |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
