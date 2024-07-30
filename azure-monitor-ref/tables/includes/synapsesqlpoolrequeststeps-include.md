---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: SynapseSqlPoolRequestSteps
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Category | string | The category of the log. |
| Command | string | The SQL command of the execution requests. |
| DistributionType | string | The distribution type of the execution requests. |
| EndCompileTime | datetime | The end compile time (UTC) of the execution requests. |
| EndTime | datetime | The end time (UTC) for the execution requests. |
| ErrorId | string | The errorId of the execution requests. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| LocationType | string | The location type of the execution requests. |
| LogicalServerName | string | The logical server name of the SQL DW. |
| OperationName | string | The operation associated with log record. |
| OperationType | string | The operation type of the execution requests. |
| RequestId | string | The requestId of the execution requests. |
| ResourceGroup | string | The azure resourceGroup of the SQL DW. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RowCount | int | The row count of the execution requests. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| StartTime | datetime | The startTime (UTC) of the execution requests. |
| Status | string | The status of the execution requests. |
| StepIndex | int | The step index of the execution requests. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
