---
title: Azure Monitor Logs reference - ADFSSISPackageExecutionComponentPhases
description: Reference for ADFSSISPackageExecutionComponentPhases table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# ADFSSISPackageExecutionComponentPhases

 ADF SSIS package execution component phases

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
|ExecutionId|long|Execution id|
|PackageName|string|Package name|
|TaskName|string|Task name|
|SubcomponentName|string|Subcomponent name|
|Phase|string|Phase|
|StartTime|datetime|Start time|
|EndTime|datetime|End time|
|ExecutionPath|string|Execution path|
|SourceSystem|string||
|Type|string||
|_ResourceId|string||
