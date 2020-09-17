---
title: Azure Monitor Logs reference - WindowsEvent
description: Reference for WindowsEvent table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 9/17/2020
---

# WindowsEvent

 

## Categories

- Security
## Solutions

- WEF_10xDSRE
- WinLog
- WindowsEventForwarding
- WEF_10x
- CustomizedWindowsEventsFiltering
- InternalWindowsEvent
- WEFInternalUat




## Columns

|Column|Type|Description|
|---|---|---|
|Channel|string||
|Computer|string||
|Data|dynamic||
|EventID|int||
|EventLevel|int||
|EventLevelName|string||
|ManagementGroupName|string||
|Provider|string||
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|Task|int||
|TimeGenerated|datetime||
|Type|string|The name of the table|
