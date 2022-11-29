---
title: Azure Monitor Logs reference - AppSystemEvents
description: Reference for AppSystemEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
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
| EventType | string | Event type |
| Measurements | dynamic | Event measurements. |
| Name | string | Event name |
| Properties | dynamic | Event properties. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Date and time when the system event was recorded. |
| Type | string | The name of the table |
