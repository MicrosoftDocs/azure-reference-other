---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: AZMSKafkaCoordinatorLogs
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| ClientId | string | The client ID. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Message | string | The Informational or warning message, which provides detailes about actions done during the group coordiantion. |
| NamespaceName | string | The namespace name. |
| Operation | string | The name of operation that done during the group coordination. |
| Provider | string | Event provider name. Possible values: eventhub, relay, and servicebus. |
| RequestId | string | The request ID, which is used for tracking purposes. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The event generation time(UTC). |
| Type | string | The name of the table |
