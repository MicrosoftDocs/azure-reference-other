---
title: Azure Monitor Logs reference - AppServiceAppLogs
description: Reference for AppServiceAppLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 2/20/2020
---

# AppServiceAppLogs

 Logs generated through your application and pushed to Azure Monitoring.

## Columns

|Column|Type|Description|
|---|---|---|
|TenantId|string||
|SourceSystem|string||
|TimeGenerated|datetime|Time when event is generated|
|Category|string|Log category name|
|Level|string|Verbosity level of log mapped to standard levels|
|Host|string|Host where the application is running|
|ResultDescription|string|Log message description|
|CustomLevel|string|Verbosity level of log emitted from application|
|Source|string|Application source from where log message is emitted|
|Method|string|Application Method from where log message is emitted|
|Logger|string|Application logger used to emit log message|
|WebSiteInstanceId|string|Instance Id the application running|
|ExceptionClass|string|Application class from where log message is emitted |
|Message|string|Log message|
|Stacktrace|string|Complete stack trace of the log message in case of exception|
|Type|string||
|_ResourceId|string||
