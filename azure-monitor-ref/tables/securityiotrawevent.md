---
title: Azure Monitor Logs reference - SecurityIoTRawEvent
description: Reference for SecurityIoTRawEvent table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 7/10/2023
---

# SecurityIoTRawEvent

 

## Categories

- Security
## Solutions

- AzureSecurityOfThings




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AgentVersion | string |  |
| AssociatedResourceId | string |  |
| AzureSubscriptionId | string |  |
| _BilledSize | real | The record size in bytes |
| DeviceId | string |  |
| EventDetails | string |  |
| IoTRawEventId | string |  |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is *false* ingestion isn't billed to your Azure account |
| IsEmpty | bool |  |
| RawEventCategory | string |  |
| RawEventName | string |  |
| RawEventType | string |  |
| TimeGenerated | datetime |  |
| TimeStamp | datetime |  |
| Type | string | The name of the table |
