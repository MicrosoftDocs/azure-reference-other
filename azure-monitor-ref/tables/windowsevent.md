---
title: Azure Monitor Logs reference - WindowsEvent
description: Reference for WindowsEvent table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 1/18/2023
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
| Channel | string | The channel to which the event was logged. |
| Computer | string | The name of the computer on which the event occurred. |
| EventData | dynamic | Contains the event data parsed to dynamic type. If the parsing fails then this field will contain null and the RawEventData field will be populated. |
| EventID | int | The identifier that the provider used to identify the event. |
| EventLevel | int | Contains the severity level of the event. |
| EventLevelName | string | The rendered message string of the level specified in the event. |
| EventOriginId | string | The unique ID of the original event |
| ManagementGroupName | string | Additional information based on the resource type. |
| Provider | string | System Properties Type - Identifies the provider that logged the event. |
| RawEventData | string | The raw event XML when parsing fails. It's null when parsing successful. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| Task | int | The task defined in the event. |
| TenantId | string |  |
| TimeGenerated | datetime | The time stamp when the event was generated on the computer. |
| Type | string | The name of the table |
