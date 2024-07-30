---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: DatabricksDataMonitoring
---


| Column | Type | Description |
|---|---|---|
| ActionName | string | The action name. |
| _BilledSize | real | The record size in bytes |
| Category | string | The category of the log. |
| Identity | dynamic | The identity of the user who performed the operation. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| LogId | string | The log ID in Databricks domain. |
| OperationName | string | The operation associated with log record. |
| OperationVersion | string | The API version of the operation. |
| RequestId | string | The request ID. |
| RequestParams | dynamic | The request parameters. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Response | dynamic | The response. |
| ServiceName | string | The service name. |
| SessionId | string | The session ID. |
| SourceIpAddress | string | The IP address of the client that performed the operation. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
| UserAgent | string | The user agent. |
