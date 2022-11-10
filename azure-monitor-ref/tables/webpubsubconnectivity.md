---
title: Azure Monitor Logs reference - WebPubSubConnectivity
description: Reference for WebPubSubConnectivity table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# WebPubSubConnectivity

 Connectivity logs provide detailed information for Azure Web PubSub hub connections. For example, basic information (user ID, connection ID, and so on) and event information (connect, disconnect, and abort event, and so on) and can be used to troubleshoot connection-related issues.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- SignalR Service WebPubSub




## Columns

| Column | Type | Description |
| --- | --- | --- |
| CallerIpAddress | string | The IP of the client or server connects to Web PubSub service. |
| ConnectionId | string | The unique identifier of the connection connected to service. |
| Level | string | The level of the log. Can be 'Informational', 'Warning', 'Error' or 'Critical'. |
| Location | string | The location of Azure Web PubSub service. |
| Message | string | The message of the log event. It provides details about the event. |
| OperationName | string | The operation of the log event. It can be used to filter the log based on a specific operation name. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of the log. |
| Type | string | The name of the table |
| UserId | string | The unique identifier of the user. It is defined by the client or app server. |
