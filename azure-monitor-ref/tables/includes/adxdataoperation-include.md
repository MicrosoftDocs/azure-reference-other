---
ms.service: azure-monitor
ms.topic: include
ms.date: 08/04/2024
ms.author: orens
author: osalzberg
ms.custom: ADXDataOperation
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Category | string | The category of this log for this events it will be DataOperation |
| CorrelationId | string | The client request id |
| DatabaseName | string | The name of the database related to this data operation |
| DataOperationKind | string | The kind of the data operation activity |
| Duration | string | Data operation duration |
| ExtentCount | int | The total number of extents ingested on this operation |
| ExtentSize | long | The size of extents (compressed size + index size) ingested (in bytes) |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| OperationName | string | The name of this operation |
| OriginalSize | long | The original size of data ingested (in bytes) |
| Principal | string | The principal that invoked the data operation |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RootActivityId | string | The root activity id |
| RowCount | long | The number of rows ingested |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TableName | string | The name of the table related to this data operation |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The time (UTC) at which this event was generated |
| TotalCPU | string | Total CPU duration |
| Type | string | The name of the table |
