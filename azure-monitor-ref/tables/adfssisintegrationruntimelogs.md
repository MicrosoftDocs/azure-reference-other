---
title: Azure Monitor Logs reference - ADFSSISIntegrationRuntimeLogs
description: Reference for ADFSSISIntegrationRuntimeLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# ADFSSISIntegrationRuntimeLogs

 ADF SSIS integration runtime logs

## Solutions

- LogManagement




## Columns

|Column|Type|Description|
|---|---|---|
|TenantId|string||
|TimeGenerated|datetime|The timestamp (UTC) of the log|
|OperationName|string|The name of the operation represented by this event|
|Category|string|The name of the log that belongs to|
|CorrelationId|string|correlation id|
|DataFactoryName|string|Data factory name|
|IntegrationRuntimeName|string|Integration runtime name|
|Level|string|Verbosity level of log|
|ResultType|string|Status of the log|
|Message|string|Event message|
|SourceSystem|string||
|Type|string||
|_ResourceId|string||
