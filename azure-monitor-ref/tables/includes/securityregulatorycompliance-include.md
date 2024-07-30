---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: SecurityRegulatoryCompliance
---


| Column | Type | Description |
|---|---|---|
| AssessedResourceId | string | The ID of the assessed resource |
| _BilledSize | real | The record size in bytes |
| ComplianceControl | string | The name of regulatory compliance control |
| ComplianceStandard | string | The name of compliance standard |
| FailedResources | int | The number of resources that failed this assessment |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| IsSnapshot | bool | Indicates whether the data was exported as part of a snapshot when 'true', or streamed in real-time when 'false'. |
| PassedResources | int | The number of resources that passed this assessment |
| Properties | dynamic | The complete set of metadata. |
| RecommendationId | string | The ID of the assessed recommendation |
| RecommendationLink | string | A link for more details on the assessment result |
| RecommendationName | string | Recommendation display name |
| RegulatoryComplianceSubscriptionId | string | The subscription ID of the assessed resource |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResourceProviderType | string | Resource provider type of the assessed resource |
| SkippedResources | int | The number of resources that passed this assessment |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| State | string | The assessment state |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The (UTC) date and time the assessment was generated |
| Type | string | The name of the table |
