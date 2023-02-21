---
title: Azure Monitor Logs reference - StorageMoverJobRunLogs
description: Reference for StorageMoverJobRunLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 2/16/2023
---

# StorageMoverJobRunLogs

 Logs associated with Storage Mover job runs.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Azure Storage Mover




## Columns

| Column | Type | Description |
| --- | --- | --- |
| JobRunName | string | JobRunName |
| Level | string | The log level. Can be Informational, Warning or Error. |
| Message | string | Log message. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| StatusCode | string | Status code associated with the log message. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Time in UTC when the log was generated on the Storage Mover agent. |
| Type | string | The name of the table |
