---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: OLPSupplyChainEvents
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| CorrelationId | string | Unique identifier to be used to correlate logs with OLPSupplyChainEntityOperations. |
| DurationMs | real | Time it took to service the REST API request, in milliseconds. |
| EventBody | dynamic | The event body. |
| EventId | string | Unique identifier for each event. |
| EventType | string | The type of the event, can be Microsoft.OpenLogisticsPlatform.EntityCreated, Microsoft.OpenLogisticsPlatform.EntityUpdated etc. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| OperationName | string | The operation name for which the log entry was created. |
| RequestId | string | Unique identifier to be used to correlate request logs. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| SupplyChainResourceType | string | The type of supplychain resource for which the event is generated, can be Item, Warehouse, WarehouseItem etc. |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (UTC) when the log was created. |
| Type | string | The name of the table |
