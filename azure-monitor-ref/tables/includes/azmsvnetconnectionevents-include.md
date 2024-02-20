---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: AZMSVnetConnectionEvents
---


| Column | Type | Description |
|---|---|---|
| Action | string | Action done by the service when evaluating connection requests. Supported actions are accept connection and deny connection. |
| AddressIp | string | IP address of a client connecting to the Event Hubs or Service Bus service. |
| _BilledSize | real | The record size in bytes |
| Count | int | Number of occurrences for the given action. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Message | string | Provides a reason why the action was done. |
| NamespaceName | string | Name of Event Hubs or Service Bus namespace. |
| Provider | string | Event provider name. Possible values: eventhub, relay, and servicebus. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The event generation time (UTC). |
| Type | string | The name of the table |
