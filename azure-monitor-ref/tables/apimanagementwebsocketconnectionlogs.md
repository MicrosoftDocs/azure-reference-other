---
title: Azure Monitor Logs reference - ApiManagementWebSocketConnectionLogs
description: Reference for ApiManagementWebSocketConnectionLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/1/2023
---

# ApiManagementWebSocketConnectionLogs

 Websocket connection logs provides logs on websocket connection events for API Management Gateway. Logging starts when the request arrives to API Management Gateway for handshake and till the request gets terminated. Every request log can be uniquely identified with CorrelationId.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- API Management services




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real |  |
| CorrelationId | string | Unique id to group related events for a websocket request. |
| Destination | string | The destination of the request/message for the websocket connection. |
| Error | string | Error details if any for the websocket connection. |
| EventName | string | Name of the event describing the operation. |
| _IsBillable | string |  |
| Region | string | Country or region where API Management Gateway is located. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Source | string | The source of the request/message for the websocket connection. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Date and time when request processing started. |
| Type | string | The name of the table |
