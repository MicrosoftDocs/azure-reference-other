---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: ADFSSISPackageExecutionDataStatistics
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Category | string | The name of the log that belongs to |
| CorrelationId | string | correlation id |
| CreatedTime | datetime | Created time |
| DataFactoryName | string | Data factory name |
| DataflowPathIdString | string | Dataflow path Id string |
| DataflowPathName | string | Dataflow path name |
| DestinationComponentName | string | Destination component name |
| ExecutionId | long | Execution id |
| ExecutionPath | string | Execution path |
| IntegrationRuntimeName | string | Integration runtime name |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Level | string | Verbosity level of log |
| OperationName | string | The name of the operation represented by this event |
| PackageName | string | Package name |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RowsSent | long | Rows sent |
| SourceComponentName | string | Source somponent name |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TaskName | string | Task name |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of the log |
| Type | string | The name of the table |
