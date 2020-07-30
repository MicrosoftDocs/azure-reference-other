---
title: Azure Monitor Logs reference - ADFSSISPackageExecutionComponentPhases
description: Reference for ADFSSISPackageExecutionComponentPhases table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 7/30/2020
---

# ADFSSISPackageExecutionComponentPhases

 ADF SSIS package execution component phases

## Solutions

- LogManagement




## Columns

|Column|Type|Description|
|---|---|---|
|Category|string|The name of the log that belongs to|
|CorrelationId|string|correlation id|
|DataFactoryName|string|Data factory name|
|EndTime|datetime|End time|
|ExecutionId|long|Execution id|
|ExecutionPath|string|Execution path|
|IntegrationRuntimeName|string|Integration runtime name|
|Level|string|Verbosity level of log|
|OperationName|string|The name of the operation represented by this event|
|PackageName|string|Package name|
|Phase|string|Phase|
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|SourceSystem|string||
|StartTime|datetime|Start time|
|SubcomponentName|string|Subcomponent name|
|TaskName|string|Task name|
|TenantId|string||
|TimeGenerated|datetime|The timestamp (UTC) of the log|
|Type|string|The name of the table|
