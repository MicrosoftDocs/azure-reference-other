---
title: Azure Monitor Logs reference - SynapseSqlPoolExecRequests
description: Reference for SynapseSqlPoolExecRequests table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# SynapseSqlPoolExecRequests

 Information about SQL requests/queries in an Azure Synapse dedicated SQL pool.

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
| ClientCorrelationId | string | The correlation set by client/user. |
| Command | string | The SQL command of the execution requests. |
| DatabaseId | string | The databaseId of the execution requests. |
| EndCompileTime | datetime | The end compile time (UTC) of the execution requests. |
| EndTime | datetime | The end time (UTC) for the execution requests. |
| ErrorId | string | The errorId of the execution requests. |
| ExplainOutput | string | The output explain of the execution requests. |
| Label | string | The label of the execution requests. |
| LogicalServerName | string | The logical server name of the SQL DW. |
| OperationName | string | The operation associated with log record. |
| RequestId | string | The requestId of the execution requests. |
| ResourceClass | string | The resource class of the execution requests. |
| ResourceGroup | string | The azure resourceGroup of the SQL DW. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RootQueryId | string | The rootQueryId of the execution requests. |
| ScopeDepth | int | The scope depth of the execution requests. |
| SourceSystem | string |  |
| StartTime | datetime | The startTime (UTC) of the execution requests. |
| StatementType | string | The statement type of the execution requests. |
| Status | string | The status of the execution requests. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
