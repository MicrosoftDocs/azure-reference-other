---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: AZMSHybridConnectionsEvents
---


| Column | Type | Description |
|---|---|---|
| ActivityId | string | Internal ID, used to identify the specified activity. |
| _BilledSize | real | The record size in bytes |
| Endpoint | string | The endpoint identifier. Can be sender or receiver. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Message | string | The details on performed task. |
| OperationName | string | The type of the Hybrid Connections operation that is being logged. |
| Provider | string | Event provider name. Possible values: eventhub, relay, and servicebus. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The log generation time (UTC). |
| Type | string | The name of the table |
