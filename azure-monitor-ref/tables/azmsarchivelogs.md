---
title: Azure Monitor Logs reference - AZMSArchiveLogs
description: Reference for AZMSArchiveLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
---

# AZMSArchiveLogs

 Captures information about Event Hubs capture operations, specifically, logs related to capture errors.

## Categories

- Azure Resources
- Audit
## Solutions

- LogManagement
## Resource types

- Event Hubs




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ActivityId | string | Internal ID, used for tracking. |
| ArchiveStep | string | The possible values: ArchiveFlushWriter, DestinationInit. |
| _BilledSize | real |  |
| DurationMs | int | The duration of failure (in Milliseconds). |
| EventhubName | string | The Event Hubs full name(includes namespace name). |
| Failures | int | The number of occurrence of failures. |
| _IsBillable | string |  |
| Message | string | Error message. |
| PartitionId | int | The Event Hubs partition being written to. |
| Provider | string | Event provider name. Possible values: eventhub, relay, and servicebus. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TaskName | string | The description of the task that failed. |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The event generation time (UTC). |
| TrackingId | string | Internal ID, used for tracking. |
| Type | string | The name of the table |
