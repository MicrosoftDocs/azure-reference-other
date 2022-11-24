---
title: Azure Monitor Logs reference - WindowsEvent
description: Reference for WindowsEvent table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# WindowsEvent

 Windows events which are collected and sent by the agent.

## Categories

- Security
## Solutions

- CustomizedWindowsEventsFiltering
- InternalWindowsEvent
- Microsoft Sentinel
- WEFInternalUat
- WEF_10x
- WEF_10xDSRE
- WinLog
- WindowsEventForwarding




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Channel | string |  |
| Computer | string |  |
| Data | dynamic |  |
| EventData | dynamic | Contains the event data parsed to dynamic type. If the parsing fails then this field will contain null and the RawEventData field will be populated. |
| EventID | int |  |
| EventLevel | int |  |
| EventLevelName | string |  |
| EventOriginId | string | The unique ID of the original event |
| ManagementGroupName | string |  |
| Provider | string |  |
| RawEventData | string | The raw event XML when parsing fails. It's null when parsing successful. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| Task | int |  |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
