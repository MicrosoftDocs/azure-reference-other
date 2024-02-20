---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: SynapseBuiltinSqlPoolRequestsEnded
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Category | string | The category of the log. |
| CorrelationId | string | A GUID used to group together a set of related events. |
| DurationMs | int | The total elapsed time in milliseconds. |
| ErrorCode | int | The error/success code |
| Identity | dynamic | A JSON blob that describes the identity of the user or application that performed the operation. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| OperationName | string | The operation associated with log record. |
| Properties | dynamic | extended properties related to this event. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultType | string | The status of the request. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
