---
title: Azure Monitor Logs reference - WindowsEvent
description: Reference for WindowsEvent table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 7/29/2021
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
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|_SubscriptionId|string|A unique identifier for the subscription that the record is associated with|
|Task|int||
|TimeGenerated|datetime||
|Type|string|The name of the table|
