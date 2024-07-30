---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: WVDAgentHealthStatus
---


| Column | Type | Description |
|---|---|---|
| ActiveSessions | string | The number of active sessions on the VM |
| AgentVersion | string | The version of the WVD Agent running on the Virtual Machine |
| AllowNewSessions | string | State of the AllowNewSession settings of the host pool |
| _BilledSize | real | The record size in bytes |
| InactiveSessions | string | The number of disconnected, or logged off sessions on the VM |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| LastHeartBeat | datetime | The time recorded when there was a change in the health status |
| LastUpgradeTimeStamp | datetime | The time recorded when there was a change in the upgrade status |
| OperationName | string | The name of the operation |
| OSVersion | string | The version of the operating system |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SessionHostHealthCheckResult | dynamic | The set of results on health checks |
| SessionHostName | string | Name of the Virtual Machine |
| SessionHostResourceId | string | The ARM path of the session host |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| Status | string | The current status of the VM, whether its healthy or not |
| StatusTimeStamp | datetime | The time recorded when there was a change in the health status |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| SxSStackVersion | string | The version of the reverse connect listener running on the VM |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Date and time when the report was generated (UTC) |
| Type | string | The name of the table |
| UpgradeErrorMsg | string | The version of the reverse connect listener running on the VM |
| UpgradeState | string | The last known state from a previous update |
