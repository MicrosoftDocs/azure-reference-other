---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: ADFSSISPackageEventMessageContext
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Category | string | The name of the log that belongs to |
| ContextDepth | int | Context depth |
| ContextSourceId | string | Context source Id |
| ContextSourceName | string | Context source name |
| ContextType | int | Context type |
| CorrelationId | string | correlation id |
| DataFactoryName | string | Data factory name |
| IntegrationRuntimeName | string | Integration runtime name |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Level | string | Verbosity level of log |
| OperationId | long | Operation id |
| OperationName | string | The name of the operation represented by this event |
| PackagePath | string | Package path |
| PropertyName | string | Property name |
| PropertyValue | dynamic | Property value |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of the log |
| Type | string | The name of the table |
