---
title: Azure Monitor Logs reference - SynapseSqlPoolDmsWorkers
description: Reference for SynapseSqlPoolDmsWorkers table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# SynapseSqlPoolDmsWorkers

 Information about workers completing DMS steps in an Azure Synapse dedicated SQL pool.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Synapse Workspaces




## Columns

| Column | Type | Description |
| --- | --- | --- |
| BytesProcessed | int | The bytes processed of the DMS workers. |
| Category | string | The category of the log. |
| CpuTime | int | The cpu time for the DMS workers. |
| DestinationInfo | string | The row count of the DMS workers. |
| DistributionId | int | The distribution id of the DMS workers. |
| DmsCpuId | int | The DMS cpu Id for the DMS workers. |
| DmsStepIndex | int | The DMS step index of the DMS workers. |
| EndTime | datetime | The end time (UTC) for the DMS workers. |
| ErrorId | string | The errorId of the DMS workers. |
| LogicalServerName | string | The logical server name of the SQL DW. |
| OperationName | string | The operation associated with log record. |
| PdwNodeId | int | The pdw node id of the DMS workers. |
| RequestId | string | The requestId of the DMS workers. |
| ResourceGroup | string | The azure resourceGroup of the SQL DW. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RowsProcessed | int | The rows processed of the DMS workers. |
| SourceInfo | string | The row count of the DMS workers. |
| SourceSystem | string |  |
| SqlSpId | int | The SQL  Sp Id for the DMS workers. |
| StartTime | datetime | The startTime (UTC) of the DMS workers. |
| Status | string | The status of the DMS workers. |
| StepIndex | int | The step index of the DMS workers. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The type of the DMS workers. |
