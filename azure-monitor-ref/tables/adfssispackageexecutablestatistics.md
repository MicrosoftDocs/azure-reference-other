---
title: Azure Monitor Logs reference - ADFSSISPackageExecutableStatistics
description: Reference for ADFSSISPackageExecutableStatistics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# ADFSSISPackageExecutableStatistics

 ADF SSIS package execution executable statistics

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
|ExecutionPath|string|Execution path|
|StartTime|datetime|Executable start time|
|EndTime|datetime|Executable end time|
|ExecutionDuration|int|Executable execution duration|
|ExecutionResult|int|Execution result|
|ExecutionValue|dynamic|Execution value|
|SourceSystem|string||
|Type|string||
|_ResourceId|string||
