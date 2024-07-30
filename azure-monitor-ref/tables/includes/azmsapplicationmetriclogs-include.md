---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: AZMSApplicationMetricLogs
---


| Column | Type | Description |
|---|---|---|
| ActivityId | string | Internal ID, used to identify the specified activity. |
| AuthId | string | Authentication ID configured for Event Hub. |
| AuthType | string | Type of authentication (Azure Active Directory or SAS Policy). |
| _BilledSize | real | The record size in bytes |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| OperationName | string | Operation performed on Event Hub (ConsumerLag, ActiveConnection, IncomingMessages, Etc.). |
| Outcome | string | Result of operation. Possible values: Success/Failure. |
| Properties | dynamic | Metadata that are specific to the operation. |
| Protocol | string | Protocol used to perform the operation. Possible value: AMQP, Kafka, and SBMP. |
| Provider | string | Event provider name. Possible values: eventhub, relay, and servicebus. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The event start time (UTC). |
| Type | string | The name of the table |
| Value | int | Value with respect to performed operation. |
