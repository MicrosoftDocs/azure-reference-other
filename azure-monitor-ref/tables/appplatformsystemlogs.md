---
title: Azure Monitor Logs reference - AppPlatformSystemLogs
description: Reference for AppPlatformSystemLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 2/20/2020
---

# AppPlatformSystemLogs

 Azure Spring Cloud System Logs

## Columns

|Column|Type|Description|
|---|---|---|
|TenantId|string||
|SourceSystem|string||
|TimeGenerated|datetime|The timestamp (UTC) of the log|
|ServiceName|string|The service name that emitted the log|
|Level|string|The level of the log|
|Thread|string|The thread of the log|
|Logger|string|The logger of the log|
|Log|string|The log of the log|
|Stack|string|The stack of the log|
|LogType|string|The type of the log|
|Category|string|Log Category|
|OperationName|string|The name of the operation represented by this event|
|Type|string||
|_ResourceId|string||
