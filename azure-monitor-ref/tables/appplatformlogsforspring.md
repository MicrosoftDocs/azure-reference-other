---
title: Azure Monitor Logs reference - AppPlatformLogsforSpring
description: Reference for AppPlatformLogsforSpring table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 7/2/2020
---

# AppPlatformLogsforSpring

 App Platform Logs for Spring

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Azure Spring Cloud




## Columns

|Column|Type|Description|
|---|---|---|
|AppName|string|The application name that emitted the log|
|Category|string|Log Category|
|InstanceName|string|The instance name that emitted the log|
|Log|string|The content of the log|
|OperationName|string|The name of the operation represented by this event|
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|ServiceName|string|The service name that emitted the log|
|SourceSystem|string||
|Stream|string|The stream of the log|
|TenantId|string||
|TimeGenerated|datetime|The timestamp (UTC) of the log|
|Type|string|The name of the table|
