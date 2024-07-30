---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: AppServiceAuthenticationLogs
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| CorrelationId | string | The ID for correlated events. |
| Details | string | The event details. |
| HostName | string | The host name of the application. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Level | string | The level of log verbosity. |
| Message | string | The log message. |
| ModuleRuntimeVersion | string | The version of App Service Authentication running. |
| OperationName | string | The name of the operation represented by this event. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SiteName | string | The runtime name of the application. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| StatusCode | int | The HTTP status code of the operation. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| SubStatusCode | int | The HTTP sub-status code of the request. |
| TaskName | string | The name of the task being performed. |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when this event was generated. |
| Type | string | The name of the table |
