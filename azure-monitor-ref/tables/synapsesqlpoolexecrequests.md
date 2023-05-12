---
title: Azure Monitor Logs reference - SynapseSqlPoolExecRequests
description: Reference for SynapseSqlPoolExecRequests table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 5/4/2023
---

# SynapseSqlPoolExecRequests

 Information about SQL requests or queries in an Azure Synapse dedicated SQL pool.

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
| Importance | string | The importance of the execution requests. |
| Label | string | The label of the execution requests. |
| LogicalServerName | string | The logical server name of the SQL DW. |
| OperationName | string | The operation associated with log record. |
| RequestId | string | The requestId of the execution requests. |
| ResourceAllocationPercent | string | The resource allocation percent of the execution requests. |
| ResourceClass | string | The resource class of the execution requests. |
| ResourceGroup | string | The azure resourceGroup of the SQL DW. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultCacheHit | string | The result cache hit of the execution requests. |
| RootQueryId | string | The rootQueryId of the execution requests. |
| ScopeDepth | int | The scope depth of the execution requests. |
| SessionId | string | The Session ID of the SQL pool instance. |
| SourceSystem | string |  |
| StartTime | datetime | The startTime (UTC) of the execution requests. |
| StatementType | string | The statement type of the execution requests. |
| Status | string | The status of the execution requests. |
| SubmitTime | datetime | The submitTime (UTC) of the execution requests. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
