---
title: Azure Monitor Logs reference - WindowsEvent
description: Reference for WindowsEvent table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 4/30/2020
---

# WindowsEvent

 

## Categories

- Security
## Solutions

- CustomizedWindowsEventsFiltering
- InternalWindowsEvent
- WEFInternalUat
- WEF_10x
- WEF_10xDSRE
- WinLog
- WindowsEventForwarding




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
|_ResourceId|string||
|Task|int||
|TimeGenerated|datetime||
|Type|string||