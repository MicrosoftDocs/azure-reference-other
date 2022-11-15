---
title: Azure Monitor Logs reference - SynapseSqlPoolRequestSteps
description: Reference for SynapseSqlPoolRequestSteps table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# SynapseSqlPoolRequestSteps

 Information about request steps that compose a given SQL request/query in an Azure Synapse dedicated SQL pool.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Synapse Workspaces




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Category | string | The category of the log. |
| Command | string | The SQL command of the execution requests. |
| DistributionType | string | The distribution type of the execution requests. |
| EndCompileTime | datetime | The end compile time (UTC) of the execution requests. |
| EndTime | datetime | The end time (UTC) for the execution requests. |
| ErrorId | string | The errorId of the execution requests. |
| LocationType | string | The location type of the execution requests. |
| LogicalServerName | string | The logical server name of the SQL DW. |
| OperationName | string | The operation associated with log record. |
| OperationType | string | The operation type of the execution requests. |
| RequestId | string | The requestId of the execution requests. |
| ResourceGroup | string | The azure resourceGroup of the SQL DW. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RowCount | int | The row count of the execution requests. |
| SourceSystem | string |  |
| StartTime | datetime | The startTime (UTC) of the execution requests. |
| Status | string | The status of the execution requests. |
| StepIndex | int | The step index of the execution requests. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
