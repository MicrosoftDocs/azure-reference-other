---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: SCOMAssessmentRecommendation
---


| Column | Type | Description |
|---|---|---|
| ActionArea | string |   |
| ActionAreaId | string |   |
| AffectedObjectName | string |   |
| AffectedObjectType | string |   |
| AssessmentId | string |   |
| _BilledSize | real | The record size in bytes |
| Computer | string |   |
| CustomData | string |   |
| DatabaseName | string |   |
| Description | string |   |
| FocusArea | string |   |
| FocusAreaId | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| ManagementGroupName | string |   |
| Recommendation | string |   |
| RecommendationId | string |   |
| RecommendationResult | string |   |
| RecommendationWeight | real |   |
| Server | string |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| SqlInstanceName | string |   |
| Technology | string |   |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
