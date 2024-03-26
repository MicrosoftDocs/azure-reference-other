---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: MNFSystemSessionHistoryUpdates
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| DeviceId | string | Device ID of the Nexus cluster which was generating the log. |
| DeviceName | string | Name of the device which was generating the log. |
| DiffTimeStamp | long | Time when the diffs were generated in the Nexus cluster. This is in unix time format which is the number of seconds elapsed since January 1, 1970 UTC. |
| EventCategory | string | Event category describing the category of events on Nexus network fabric devices. |
| FabricId | string | Fabric ID of the Nexus cluster which was generating the log. |
| GnmiTimeStamp | long | Time when the log was generated in the Nexus cluster. This is in unix time format which is the number of seconds elapsed since January 1, 1970 UTC. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SessionDiffs | string | Differences in the session. |
| SessionUpdateSessionId | string | Session ID of the update. |
| SessionUpdateSize | long | Size of the session update. |
| SessionUpdateTimeStamp | long | Time when the session was updated. This is in unix time format which is the number of seconds elapsed since January 1, 1970 UTC. |
| SessionUpdateUser | string | User who updated the session. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (UTC) when the log was generated. |
| Type | string | The name of the table |
