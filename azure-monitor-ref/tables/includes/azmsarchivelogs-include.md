---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: AZMSArchiveLogs
---


| Column | Type | Description |
|---|---|---|
| ActivityId | string | Internal ID, used for tracking. |
| ArchiveStep | string | The possible values: ArchiveFlushWriter, DestinationInit. |
| _BilledSize | real | The record size in bytes |
| DurationMs | int | The duration of failure (in Milliseconds). |
| EventhubName | string | The Event Hubs full name(includes namespace name). |
| Failures | int | The number of occurrence of failures. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Message | string | Error message. |
| PartitionId | int | The Event Hubs partition being written to. |
| Provider | string | Event provider name. Possible values: eventhub, relay, and servicebus. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TaskName | string | The description of the task that failed. |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The event generation time (UTC). |
| TrackingId | string | Internal ID, used for tracking. |
| Type | string | The name of the table |
