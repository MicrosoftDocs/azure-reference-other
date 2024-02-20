---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: SQLAssessmentRecommendation
---


| Column | Type | Description |
|---|---|---|
| ActionArea | string |   |
| ActionAreaId | string |   |
| AffectedObjectName | string |   |
| AffectedObjectResult | string |   |
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
| Recommendation | string |   |
| RecommendationId | string |   |
| RecommendationResult | string |   |
| RecommendationWeight | real |   |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| SqlInstanceName | string |   |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| Technology | string |   |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
