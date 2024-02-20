---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: AZMSKafkaUserErrorLogs
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| EventhubName | string | Name of Event Hub. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Message | string | The informational message, which provides details about an error. |
| NamespaceName | string | Name of Event Hubs namespace. |
| Provider | string | Event provider name. Possible values: eventhub, relay, and servicebus. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The event start time (UTC). |
| TrackingId | string | The tracking ID, which is used for tracking purposes. |
| Type | string | The name of the table |
