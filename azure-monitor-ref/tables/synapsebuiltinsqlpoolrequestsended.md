---
title: Azure Monitor Logs reference - SynapseBuiltinSqlPoolRequestsEnded
description: Reference for SynapseBuiltinSqlPoolRequestsEnded table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
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
| _BilledSize | real |  |
| Category | string | The category of the log. |
| CorrelationId | string | A GUID used to group together a set of related events. |
| DurationMs | int | The total elapsed time in milliseconds. |
| ErrorCode | int | The error/success code |
| Identity | dynamic | A JSON blob that describes the identity of the user or application that performed the operation. |
| _IsBillable | string |  |
| OperationName | string | The operation associated with log record. |
| Properties | dynamic | extended properties related to this event. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultType | string | The status of the request. |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
