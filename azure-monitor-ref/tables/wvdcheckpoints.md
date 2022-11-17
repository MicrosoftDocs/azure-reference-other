---
title: Azure Monitor Logs reference - WVDCheckpoints
description: Reference for WVDCheckpoints table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
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
| CorrelationId | string | The correlation Id for the activity. |
| Name | string | The name of the checkpoint. |
| Parameters | dynamic | The parameters for the checkpoint. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Source | string | The component that emitted the checkpoint. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of the event. |
| Type | string | The name of the table |
| UserName | string | The user name for the activity associated with the checkpoint. |
