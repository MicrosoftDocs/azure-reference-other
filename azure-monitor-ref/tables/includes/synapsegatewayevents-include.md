---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: SynapseGatewayEvents
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Category | string | The category of the log. |
| CorrelationId | string | A GUID used to group together a set of related events. |
| Identity | dynamic | A JSON blob that describes the identity of the user or application that performed the operation. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Location | string | The region of the resource emitting the event. |
| OperationName | string | The operation associated with log record. |
| OperationVersion | string | The API Version of the operation. |
| RequestUri | string | The request URI for this query. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultDescription | string | The static text description of this operation. |
| ResultSignature | string | The sub status of the event |
| ResultType | string | Status of the event. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
