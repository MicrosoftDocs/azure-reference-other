---
title: Azure Monitor Logs reference - StorageCacheUpgradeEvents
description: Reference for StorageCacheUpgradeEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
---

# StorageCacheUpgradeEvents

 Logs for Azure HPC Cache firmware upgrade events.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Azure HPC Cache




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AvailableFirmwareVersion | string | The firmware version for upgrade, if available. |
| CorrelationId | string | Unique identifier to be used to correlate logs, if available. |
| CurrentFirmwareVersion | string | The firmware version currently running. |
| Description | string | The description of the upgrade event. |
| Location | string | The region of the resource associated with the event. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Timestamp (UTC) when the log was created. |
| Type | string | The name of the table |
