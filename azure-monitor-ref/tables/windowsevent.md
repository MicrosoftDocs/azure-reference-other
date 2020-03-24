---
title: Azure Monitor Logs reference - WindowsEvent
description: Reference for WindowsEvent table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
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
|TimeGenerated|datetime||
|Provider|string||
|Channel|string||
|Computer|string||
|Task|int||
|EventLevel|int||
|EventLevelName|string||
|Data|dynamic||
|EventID|int||
|ManagementGroupName|string||
|Type|string||
|_ResourceId|string||
