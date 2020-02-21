---
title: Azure Monitor Logs reference - AppPlatformLogsforSpring
description: Reference for AppPlatformLogsforSpring table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 2/20/2020
---

# AppPlatformLogsforSpring

 App Platform Logs for Spring

## Columns

|Column|Type|Description|
|---|---|---|
|TenantId|string||
|SourceSystem|string||
|TimeGenerated|datetime|The timestamp (UTC) of the log|
|ServiceName|string|The service name that emitted the log|
|AppName|string|The application name that emitted the log|
|InstanceName|string|The instance name that emitted the log|
|Log|string|The content of the log|
|Stream|string|The stream of the log|
|Category|string|Log Category|
|OperationName|string|The name of the operation represented by this event|
|Type|string||
|_ResourceId|string||
