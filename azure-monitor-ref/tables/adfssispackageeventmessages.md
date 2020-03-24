---
title: Azure Monitor Logs reference - ADFSSISPackageEventMessages
description: Reference for ADFSSISPackageEventMessages table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# ADFSSISPackageEventMessages

 ADF SSIS package execution event messages

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
|MessageTime|datetime|Message time|
|MessageType|int|Message type|
|MessageSourceType|int|Message source type|
|Message|string|Event message|
|ExtendedInfoId|long|Extended info id|
|PackageName|string|Package name|
|EventName|string|Event name|
|MessageSourceName|string|Message source name|
|MessageSourceId|string|Message source id|
|SubcomponentName|string|Subcomponent name|
|PackagePath|string|Package path|
|ExecutionPath|string|Execution path|
|ThreadId|int|Thread id|
|MessageCode|int|Message code|
|EventMessageGuid|string|Event message guid|
|SourceSystem|string||
|Type|string||
|_ResourceId|string||
