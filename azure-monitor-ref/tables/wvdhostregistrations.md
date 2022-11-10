---
title: Azure Monitor Logs reference - WVDHostRegistrations
description: Reference for WVDHostRegistrations table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# WVDHostRegistrations

 Windows Virtual Desktop Host Registration Activity

## Categories

- Azure Virtual Desktop
## Solutions

- LogManagement
## Resource types

- Desktop Virtualization Host Pools




## Columns

| Column | Type | Description |
| --- | --- | --- |
| CorrelationId | string | The activity Id. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SessionHostIPAddress | string | The IP address of the session host that was registered with the WVD service. |
| SessionHostName | string | The name of the session host that was registered with the WVD service. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of the event. |
| Type | string | The name of the table |
