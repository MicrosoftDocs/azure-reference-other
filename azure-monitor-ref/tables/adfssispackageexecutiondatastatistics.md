---
title: Azure Monitor Logs reference - ADFSSISPackageExecutionDataStatistics
description: Reference for ADFSSISPackageExecutionDataStatistics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# ADFSSISPackageExecutionDataStatistics

 ADF SSIS package execution data statistics

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
|DataflowPathIdString|string|Dataflow path Id string|
|DataflowPathName|string|Dataflow path name|
|SourceComponentName|string|Source somponent name|
|DestinationComponentName|string|Destination component name|
|RowsSet|long|Rows set|
|CreatedTime|datetime|Created time|
|ExecutionPath|string|Execution path|
|SourceSystem|string||
|Type|string||
|_ResourceId|string||
