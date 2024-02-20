---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: FunctionAppLogs
---


| Column | Type | Description |
|---|---|---|
| ActivityId | string | The activity ID that logged the message. |
| AppName | string | The Function application name. |
| _BilledSize | real | The record size in bytes |
| Category | string | The log category name. |
| EventId | int | The event ID. |
| EventName | string | The event name. |
| ExceptionDetails | string | The exception details. This includes the exception type, message, and stack trace. |
| ExceptionMessage | string | The exception message. |
| ExceptionType | string | The exception type (e.g., System.InvalidOperationException). |
| FunctionInvocationId | string | The invocation ID that logged the message. |
| FunctionName | string | The name of the function that logged the message. |
| HostInstanceId | string | The host instance ID. |
| HostVersion | string | The Functions host version. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Level | string | The log level. Valid values are Trace, Debug, Information, Warning, Error, or Critical. |
| LevelId | int | The integer value of the log level. Valid values are 0 (Trace), 1 (Debug), 2 (Information), 3 (Warning), 4 (Error), or 5 (Critical). |
| Location | string | The location of the server that processed the request (e.g., South Central US). |
| Message | string | The log message. |
| ProcessId | int | The process ID. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RoleInstance | string | The role instance ID. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of the log. |
| Type | string | The name of the table |
