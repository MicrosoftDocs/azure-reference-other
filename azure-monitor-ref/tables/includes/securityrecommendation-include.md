---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: SecurityRecommendation
---


| Column | Type | Description |
|---|---|---|
| AssessedResourceId | string |   |
| _BilledSize | real | The record size in bytes |
| Description | string |   |
| DeviceId | string |   |
| DiscoveredTimeUTC | datetime |   |
| Environment | string |   |
| FirstEvaluationDate | datetime |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| IsSnapshot | bool |   |
| PolicyDefinitionId | string |   |
| Properties | dynamic |   |
| ProviderName | string |   |
| RecommendationAdditionalData | dynamic |   |
| RecommendationDisplayName | string |   |
| RecommendationId | string |   |
| RecommendationName | string |   |
| RecommendationSeverity | string |   |
| RecommendationState | string |   |
| ResolvedTimeUTC | datetime |   |
| ResourceRegion | string |   |
| StatusChangeDate | datetime |   |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
