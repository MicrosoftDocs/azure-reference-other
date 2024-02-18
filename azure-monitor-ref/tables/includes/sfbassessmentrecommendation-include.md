---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: SfBAssessmentRecommendation
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
| Description | string |   |
| Domain | string |   |
| FocusArea | string |   |
| FocusAreaId | string |   |
| Forest | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| LyncCentralMgmtStoreDatabase | string |   |
| LyncFEPool | string |   |
| LyncFrontEnd | string |   |
| LyncInternalDomain | string |   |
| LyncOrganization | string |   |
| LyncSimpleURLDomain | string |   |
| LyncSite | string |   |
| LyncUserStoreDatabase | string |   |
| Recommendation | string |   |
| RecommendationId | string |   |
| RecommendationResult | string |   |
| RecommendationWeight | real |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| Technology | string |   |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
