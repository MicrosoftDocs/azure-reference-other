---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: ContainerRegistryLoginEvents
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| CallerIpAddress | string |   |
| Category | string |   |
| CorrelationId | string |   |
| DurationMs | string |   |
| Identity | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| JwtId | string |   |
| LoginServer | string |   |
| OperationName | string |   |
| Region | string |   |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultDescription | string |   |
| ResultType | string |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
| UserAgent | string |   |
