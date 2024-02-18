---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: ApiManagementWebSocketConnectionLogs
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| CorrelationId | string | Unique id to group related events for a websocket request. |
| Destination | string | The destination of the request/message for the websocket connection. |
| Error | string | Error details if any for the websocket connection. |
| EventName | string | Name of the event describing the operation. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Region | string | Country or region where API Management Gateway is located. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Source | string | The source of the request/message for the websocket connection. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Date and time when request processing started. |
| Type | string | The name of the table |
