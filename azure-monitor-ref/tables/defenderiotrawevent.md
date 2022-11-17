---
title: Azure Monitor Logs reference - DefenderIoTRawEvent
description: Reference for DefenderIoTRawEvent table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
---

# DefenderIoTRawEvent

 Table is part of Microsoft Defender for IoT. It contains IoT security raw event properties of new and future events. These logs can be used to monitor your new operational, diagnostic and security raw events.

## Solutions

- AzureSecurityOfThings




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AgentVersion | string | The version of the agent. |
| AssociatedResourceId | string | The associated Azure resource ID. |
| AzureSubscriptionId | string | The Azure subscription ID. |
| DeviceId | string | The device ID. |
| EventDetails | dynamic | Additional raw event details. |
| IoTRawEventId | string | The internal raw event ID. |
| IsEmpty | bool | Property identifying if the raw event contains data. |
| RawEventCategory | string | The category of the raw event - periodic or triggered. |
| RawEventName | string | The name of the raw event. |
| RawEventType | string | The type of the raw event - security, operational or diagnostic. |
| TimeGenerated | datetime | The date and time the raw event was generated. |
| TimeStamp | datetime | The date and time the raw event was first detected. |
| Type | string | The name of the table |
