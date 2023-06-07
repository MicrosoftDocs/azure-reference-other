---
title: Azure Monitor Logs reference - AppSystemEvents
description: Reference for AppSystemEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/1/2023
---

# AppSystemEvents

 Application Insights system events.

## Categories

- Applications
## Solutions

- LogManagement
## Resource types

- Application Insights




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real |  |
| EventType | string | Event type |
| _IsBillable | string |  |
| Measurements | dynamic | Event measurements. |
| Name | string | Event name |
| Properties | dynamic | Event properties. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Date and time when the system event was recorded. |
| Type | string | The name of the table |
