---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: AZMSCustomerManagedKeyUserLogs
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Category | string | Type of category for a message. It's one of the following values: error and info. For example, if the key from your key vault is being disabled, then it would be an information category or if a key can't be unwrapped, it could fall under error. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Key | string | The name of the key-vault key that's used to encrypt the Event Hubs namespace. |
| KeyVault | string | The name of the key vault resource. |
| Message | string | The message, which provides detailes about an error or informational message. |
| Operation | string | The operation that's performed on the key in your key vault. For example, disable/enable the key, wrap, or unwrap. |
| Provider | string | Event provider name. Possible values: eventhub, relay, and servicebus. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| StatusCode | string | The code that's associated with the operation. Example: Error code, 404 means that key wasn't found. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The event start time(UTC). |
| Type | string | The name of the table |
| Version | string | The version of the key-vault key. |
