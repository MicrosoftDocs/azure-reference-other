---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: DatabricksGitCredentials
---


| Column | Type | Description |
|---|---|---|
| ActionName | string | The action of the request. |
| _BilledSize | real | The record size in bytes |
| Category | string | The service that logged the request. |
| Identity | dynamic | Information about the user that makes the requests. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| LogId | string | The unique identifier for the log messages. |
| OperationName | string | The action, such as login, logout, read, write, etc. |
| OperationVersion | string | The Databricks schema version of the diagnostic log format. |
| RequestId | string | Unique request ID. |
| RequestParams | dynamic | Parameter key-value pairs used in the event. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Response | dynamic | The HTTP response to the request, including error message (if applicable), result, and statusCode. |
| ServiceName | string | The service of the source request. |
| SessionId | string | Session ID of the action. |
| SourceIPAddress | string | The IP address of the source request. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp of the action (UTC). |
| Type | string | The name of the table |
| UserAgent | string | The browser or API client used to make the request. |
