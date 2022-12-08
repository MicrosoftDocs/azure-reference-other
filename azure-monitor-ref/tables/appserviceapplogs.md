---
title: Azure Monitor Logs reference - AppServiceAppLogs
description: Reference for AppServiceAppLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/8/2022
---

# AppServiceAppLogs

 Logs generated through your application.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- App Services




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Category | string | Log category name |
| ContainerId | string | Application container id |
| CustomLevel | string | Verbosity level of log |
| ExceptionClass | string | Application class from where log message is emitted  |
| Host | string | Host where the application is running |
| Level | string | Verbosity level of log mapped to standard levels (Informational, Warning, Error, or Critical) |
| Logger | string | Application logger used to emit log message |
| Message | string | Log message |
| Method | string | Application Method from where log message is emitted |
| OperationName | string | The name of the operation represented by this event. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultDescription | string | Log message description |
| Source | string | Application source from where log message is emitted |
| SourceSystem | string |  |
| Stacktrace | string | Complete stack trace of the log message in case of exception |
| StackTrace | string | Complete stack trace of the log message in case of exception |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Time when event is generated |
| Type | string | The name of the table |
| WebSiteInstanceId | string | Instance Id the application running |
