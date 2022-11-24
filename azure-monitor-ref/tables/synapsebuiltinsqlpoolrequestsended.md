---
title: Azure Monitor Logs reference - SynapseBuiltinSqlPoolRequestsEnded
description: Reference for SynapseBuiltinSqlPoolRequestsEnded table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# SynapseBuiltinSqlPoolRequestsEnded

 Ended Azure Synapse built-in serverless SQL requests.

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
| CorrelationId | string | A GUID used to group together a set of related events. |
| DurationMs | int | The total elapsed time in milliseconds. |
| ErrorCode | int | The error/success code |
| Identity | dynamic | A JSON blob that describes the identity of the user or application that performed the operation. |
| OperationName | string | The operation associated with log record. |
| Properties | dynamic | extended properties related to this event. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultType | string | The status of the request. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
