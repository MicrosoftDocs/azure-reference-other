---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: SecureScores
---


| Column | Type | Description |
|---|---|---|
| AssessedResourceId | string | The ID of the assessed resource |
| _BilledSize | real | The record size in bytes |
| CurrentScore | real | The current secure score per control |
| DisplayName | string | The initiative�s name |
| Environment | string | Data source environment. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| IsSnapshot | bool | Indicates whether the data was exported as part of a snapshot when 'true', or streamed in real-time when 'false'. |
| MaxScore | int | The maximum control score |
| PercentageScore | real | The percentage of the score (current score divided by max score) |
| Properties | dynamic | The complete set of metadata. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResourceProviderType | string | Resource provider type of the assessed resource |
| SecureScoresSubscriptionId | string | The ID of the subscription |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The (UTC) date and time the control score was generated |
| Type | string | The name of the table |
| Weight | long | The weight for calculation of an aggregated score for several scopes |
