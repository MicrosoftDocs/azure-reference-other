---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: WVDErrors
---


| Column | Type | Description |
|---|---|---|
| ActivityType | string | The activity type for which the error happened. |
| _BilledSize | real | The record size in bytes |
| Code | long | The error code for the error. |
| CodeSymbolic | string | The error code symbolic representation (if available). |
| CorrelationId | string | The activity Id. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Message | string | The error message. |
| Operation | string | The name of the operation that failed. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ServiceError | bool | Indicator whether this is a service or customer error. |
| Source | string | The source of the error. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of the event. |
| Type | string | The name of the table |
| UserName | string | The user for which the error happened. |
