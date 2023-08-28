---
ms.service: azure-monitor
ms.topic: include
ms.date: 08/28/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: SecurityIoTRawEvent
---


| Column | Type | Description |
|---|---|---|
| AgentVersion | string |   |
| AssociatedResourceId | string |   |
| AzureSubscriptionId | string |   |
| _BilledSize | real | The record size in bytes |
| DeviceId | string |   |
| EventDetails | string |   |
| IoTRawEventId | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| IsEmpty | bool |   |
| RawEventCategory | string |   |
| RawEventName | string |   |
| RawEventType | string |   |
| TimeGenerated | datetime |   |
| TimeStamp | datetime |   |
| Type | string | The name of the table |
