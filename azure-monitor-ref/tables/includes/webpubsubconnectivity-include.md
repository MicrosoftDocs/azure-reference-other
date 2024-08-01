---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: WebPubSubConnectivity
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| CallerIpAddress | string | The IP of the client or server connects to Web PubSub service. |
| ConnectionId | string | The unique identifier of the connection connected to service. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Level | string | The level of the log. Can be 'Informational', 'Warning', 'Error' or 'Critical'. |
| Location | string | The location of Azure Web PubSub service. |
| Message | string | The message of the log event. It provides details about the event. |
| OperationName | string | The operation of the log event. It can be used to filter the log based on a specific operation name. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of the log. |
| Type | string | The name of the table |
| UserId | string | The unique identifier of the user. It is defined by the client or app server. |
