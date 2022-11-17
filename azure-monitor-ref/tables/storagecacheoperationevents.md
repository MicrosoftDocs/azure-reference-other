---
title: Azure Monitor Logs reference - StorageCacheOperationEvents
description: Reference for StorageCacheOperationEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
---

# StorageCacheOperationEvents

 Logs for Azure HPC Cache API requests.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Azure HPC Cache




## Columns

| Column | Type | Description |
| --- | --- | --- |
| CorrelationId | string | Unique identifier to be used to correlate logs, if available. |
| Location | string | The region of the resource associated with the event. |
| OperationName | string | The operation name for which the log entry was created. |
| PrimingJobName | string | Name of the priming job associated with the operation, if available. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResponseCode | int | HTTP status of API request. |
| ResultDescription | string | Details about the result, if available. |
| ResultType | string | Result of the REST API request. |
| SourceSystem | string |  |
| StorageTargetName | string | Name of the storage target associated with the operation, if available. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Timestamp (UTC) when the log was created. |
| Type | string | The name of the table |
