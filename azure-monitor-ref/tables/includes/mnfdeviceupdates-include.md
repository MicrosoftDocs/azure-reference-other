---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: MNFDeviceUpdates
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| DeviceId | string | Device ID of the Nexus cluster which was generating the log. |
| DeviceTime | long | Time when the log was generated in the Nexus cluster. This is in unix time format which is the number of seconds elapsed since January 1, 1970 UTC. |
| EventCategory | string | Event category describing the category of events on Nexus network fabric devices. |
| EventName | string | Event name describing the update performed on Nexus network fabric devices. |
| FabricId | string | Fabric ID of the Nexus cluster which was generating the log. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Properties | dynamic | Properties of the log. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (UTC) when the log was generated. |
| Type | string | The name of the table |
