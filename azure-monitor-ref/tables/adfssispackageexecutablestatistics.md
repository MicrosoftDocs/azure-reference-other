---
title: Azure Monitor Logs reference - ADFSSISPackageExecutableStatistics
description: Reference for ADFSSISPackageExecutableStatistics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/1/2022
---

# ADFSSISPackageExecutableStatistics

 ADF SSIS package execution executable statistics

## Solutions

- LogManagement
## Resource types

- Data factories




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Category | string | The name of the log that belongs to |
| CorrelationId | string | correlation id |
| DataFactoryName | string | Data factory name |
| EndTime | datetime | Executable end time |
| ExecutionDuration | int | Executable execution duration |
| ExecutionId | long | Execution id |
| ExecutionPath | string | Execution path |
| ExecutionResult | int | Execution result |
| ExecutionValue | dynamic | Execution value |
| IntegrationRuntimeName | string | Integration runtime name |
| Level | string | Verbosity level of log |
| OperationName | string | The name of the operation represented by this event |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| StartTime | datetime | Executable start time |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of the log |
| Type | string | The name of the table |
