---
title: Azure Monitor Logs reference - ADFSSISPackageExecutionDataStatistics
description: Reference for ADFSSISPackageExecutionDataStatistics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/1/2022
---

# ADFSSISPackageExecutionDataStatistics

 ADF SSIS package execution data statistics

## Solutions

- LogManagement
## Resource types

- Data factories




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Category | string | The name of the log that belongs to |
| CorrelationId | string | correlation id |
| CreatedTime | datetime | Created time |
| DataFactoryName | string | Data factory name |
| DataflowPathIdString | string | Dataflow path Id string |
| DataflowPathName | string | Dataflow path name |
| DestinationComponentName | string | Destination component name |
| ExecutionId | long | Execution id |
| ExecutionPath | string | Execution path |
| IntegrationRuntimeName | string | Integration runtime name |
| Level | string | Verbosity level of log |
| OperationName | string | The name of the operation represented by this event |
| PackageName | string | Package name |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RowsSent | long | Rows sent |
| SourceComponentName | string | Source somponent name |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TaskName | string | Task name |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of the log |
| Type | string | The name of the table |
