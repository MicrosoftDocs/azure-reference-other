---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: DefenderIoTRawEvent
---


| Column | Type | Description |
|---|---|---|
| AgentVersion | string | The version of the agent. |
| AssociatedResourceId | string | The associated Azure resource ID. |
| AzureSubscriptionId | string | The Azure subscription ID. |
| _BilledSize | real | The record size in bytes |
| DeviceId | string | The device ID. |
| EventDetails | dynamic | Additional raw event details. |
| IoTRawEventId | string | The internal raw event ID. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| IsEmpty | bool | Property identifying if the raw event contains data. |
| RawEventCategory | string | The category of the raw event - periodic or triggered. |
| RawEventName | string | The name of the raw event. |
| RawEventType | string | The type of the raw event - security, operational or diagnostic. |
| TimeGenerated | datetime | The date and time the raw event was generated. |
| TimeStamp | datetime | The date and time the raw event was first detected. |
| Type | string | The name of the table |
