---
title: Azure Monitor Logs reference - AppSystemEvents
description: Reference for AppSystemEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
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

|Column|Type|Description|
|---|---|---|
|TenantId|string||
|TimeGenerated|datetime|Date and time when the system event was recorded.|
|EventType|string|Event type|
|Name|string|Event name|
|Properties|dynamic|Event properties.|
|Measurements|dynamic|Event measurements.|
|SourceSystem|string||
|Type|string||
|_ResourceId|string||
