---
title: Azure Monitor Logs reference - WVDCheckpoints
description: Reference for WVDCheckpoints table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
---

# WVDCheckpoints

 Windows Virtual Desktop Checkpoint Activity

## Categories

- Azure Virtual Desktop
## Solutions

- LogManagement
## Resource types

- Desktop Virtualization Host Pools
- Desktop Virtualization Application Groups
- Desktop Virtualization workspaces




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ActivityType | string | The type of activity for which this checkpoint was reported. |
| _BilledSize | real |  |
| CorrelationId | string | The correlation Id for the activity. |
| _IsBillable | string |  |
| Name | string | The name of the checkpoint. |
| Parameters | dynamic | The parameters for the checkpoint. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Source | string | The component that emitted the checkpoint. |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of the event. |
| Type | string | The name of the table |
| UserName | string | The user name for the activity associated with the checkpoint. |
