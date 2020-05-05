---
title: Azure Monitor Logs reference - AppServiceAppLogs
description: Reference for AppServiceAppLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 4/30/2020
---

# AppServiceAppLogs

 Logs generated through your application and pushed to Azure Monitoring.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- App Service




## Columns

|Column|Type|Description|
|---|---|---|
|Category|string|Log category name|
|CustomLevel|string|Verbosity level of log emitted from application|
|ExceptionClass|string|Application class from where log message is emitted |
|Host|string|Host where the application is running|
|Level|string|Verbosity level of log mapped to standard levels|
|Logger|string|Application logger used to emit log message|
|Message|string|Log message|
|Method|string|Application Method from where log message is emitted|
|_ResourceId|string||
|ResultDescription|string|Log message description|
|Source|string|Application source from where log message is emitted|
|SourceSystem|string||
|Stacktrace|string|Complete stack trace of the log message in case of exception|
|TenantId|string||
|TimeGenerated|datetime|Time when event is generated|
|Type|string||
|WebSiteInstanceId|string|Instance Id the application running|
