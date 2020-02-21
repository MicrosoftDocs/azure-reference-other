---
title: Azure Monitor Logs reference - systemEvents
description: Reference for systemEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 2/20/2020
---

# systemEvents

 Application Insights System Events Schema

## Columns

|Column|Type|Description|
|---|---|---|
|TenantId|string||
|TimeGenerated|datetime|Date and time when the system event was recorded.|
|type|string|Event type|
|name|string|Event name|
|dimensions|dynamic|Event dimensions.|
|measurements|dynamic|Event measurements.|
|itemId|string|Unique ID of the telemetry item assigned by the Application Insights ingestion endpoint.|
|SourceSystem|string||
|Type|string||
|_ResourceId|string||
