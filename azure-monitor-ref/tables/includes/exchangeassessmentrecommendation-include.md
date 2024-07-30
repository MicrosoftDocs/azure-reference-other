---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: ExchangeAssessmentRecommendation
---


| Column | Type | Description |
|---|---|---|
| ActionArea | string | The segment in which action is to be performed |
| ActionAreaId | string | ID generated for Action Area |
| ActiveDirectorySite | string |   |
| AffectedObjectName | string | Name of the affected object |
| AffectedObjectType | string | Type of object which is affected |
| AssessmentId | string | ID of the assessment |
| _BilledSize | real | The record size in bytes |
| Computer | string | The machine from which data is uploaded |
| CustomData | string |   |
| Description | string | Description of the recommendation |
| ExchangeAdminGroup | string |   |
| ExchangeDAG | string |   |
| ExchangeMailboxDatabase | string |   |
| ExchangeOrganization | string |   |
| ExchangePublicFolderDatabase | string |   |
| ExchangeServer | string |   |
| FocusArea | string | Area to be focussed on |
| FocusAreaId | string | ID of the Focus Area |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Recommendation | string | Generated recommendation |
| RecommendationId | string | ID of the recommendation generated |
| RecommendationResult | string | Result of the recommendation generated |
| RecommendationWeight | real | Weight of recommendation |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| Technology | string |   |
| TimeGenerated | datetime | Date and time the record was created. |
| Type | string | The name of the table |
