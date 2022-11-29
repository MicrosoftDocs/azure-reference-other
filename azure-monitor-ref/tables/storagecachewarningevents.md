---
title: Azure Monitor Logs reference - StorageCacheWarningEvents
description: Reference for StorageCacheWarningEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# StorageCacheWarningEvents

 Logs for Azure HPC Cache warning events.

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
| Description | string | The description of the warning event. |
| Level | string | The severity level of the event: Informational, Warning, Error, or Critical. |
| Location | string | The region of the resource associated with the event. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| State | string | The state of the warning: Active or Cleared. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Timestamp (UTC) when the log was created. |
| Type | string | The name of the table |
