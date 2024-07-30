---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: ContainerRegistryRepositoryEvents
---


| Column | Type | Description |
|---|---|---|
| ArtifactType | string |   |
| _BilledSize | real | The record size in bytes |
| CallerIpAddress | string |   |
| Category | string |   |
| CorrelationId | string |   |
| Digest | string |   |
| DurationMs | string |   |
| Identity | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| LoginServer | string |   |
| MediaType | string |   |
| OperationName | string |   |
| Region | string |   |
| Repository | string |   |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultDescription | string |   |
| ResultType | string |   |
| Size | int |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| Tag | string |   |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
| UserAgent | string |   |
| UserTenantId | string |   |
