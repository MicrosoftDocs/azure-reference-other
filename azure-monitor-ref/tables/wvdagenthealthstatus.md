---
title: Azure Monitor Logs reference - WVDAgentHealthStatus
description: Reference for WVDAgentHealthStatus table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
---

# WVDAgentHealthStatus

 Azure Virtual Desktop agent health status.

## Solutions

- LogManagement
## Resource types

- Desktop Virtualization Host Pools




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ActiveSessions | string | The number of active sessions on the VM |
| AgentVersion | string | The version of the WVD Agent running on the Virtual Machine |
| AllowNewSessions | string | State of the AllowNewSession settings of the host pool |
| InactiveSessions | string | The number of disconnected, or logged off sessions on the VM |
| LastHeartBeat | datetime | The time recorded when there was a change in the health status |
| LastUpgradeTimeStamp | datetime | The time recorded when there was a change in the upgrade status |
| OperationName | string | The name of the operation |
| OSVersion | string | The version of the operating system |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SessionHostHealthCheckResult | dynamic | The set of results on health checks |
| SessionHostName | string | Name of the Virtual Machine |
| SessionHostResourceId | string | The ARM path of the session host |
| SourceSystem | string |  |
| Status | string | The current status of the VM, whether its healthy or not |
| StatusTimeStamp | datetime | The time recorded when there was a change in the health status |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| SxSStackVersion | string | The version of the reverse connect listener running on the VM |
| TenantId | string |  |
| TimeGenerated | datetime | Date and time when the report was generated (UTC) |
| Type | string | The name of the table |
| UpgradeErrorMsg | string | The version of the reverse connect listener running on the VM |
| UpgradeState | string | The last known state from a previous update |
