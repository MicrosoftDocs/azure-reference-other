---
title: Azure Monitor Logs reference - ADFSSISPackageEventMessageContext
description: Reference for ADFSSISPackageEventMessageContext table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# ADFSSISPackageEventMessageContext

 ADF SSIS package execution event message context

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
|OperationId|long|Operation id|
|ContextDepth|int|Context depth|
|PackagePath|string|Package path|
|ContextType|int|Context type|
|ContextSourceName|string|Context source name|
|ContextSourceId|string|Context source Id|
|PropertyName|string|Property name|
|PropertyValue|dynamic|Property value|
|SourceSystem|string||
|Type|string||
|_ResourceId|string||
