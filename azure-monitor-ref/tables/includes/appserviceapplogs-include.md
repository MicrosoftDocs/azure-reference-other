---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: AppServiceAppLogs
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Category | string | Log category name |
| ContainerId | string | Application container id |
| CustomLevel | string | Verbosity level of log |
| ExceptionClass | string | Application class from where log message is emitted  |
| Host | string | Host where the application is running |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Level | string | Verbosity level of log mapped to standard levels (Informational, Warning, Error, or Critical) |
| Logger | string | Application logger used to emit log message |
| Message | string | Log message |
| Method | string | Application Method from where log message is emitted |
| OperationName | string | The name of the operation represented by this event. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultDescription | string | Log message description |
| Source | string | Application source from where log message is emitted |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| Stacktrace | string | Complete stack trace of the log message in case of exception |
| StackTrace | string | Complete stack trace of the log message in case of exception |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Time when event is generated |
| Type | string | The name of the table |
| WebSiteInstanceId | string | Instance Id the application running |
