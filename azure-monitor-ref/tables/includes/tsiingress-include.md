---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: TSIIngress
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Category | string | Category of the log event. |
| CorrelationId | string | The correlation ID of the request. |
| ErrorCode | string | The code associated with the error |
| EventSourceProperties | dynamic | A collection of properties specific to your event source. Contains details such as the consumer group and the access key name. |
| EventSourceType | string | The type of event source. It could either be Event hub or IoT hub. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Level | string | The severity level of the event. |
| Location | string | The location of the resource. |
| Message | string | The message associated with the error. Includes details on what went wrong and how to mitigate the error. |
| OperationName | string | Operation name of the event. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultDescription | string | Description of the result of the operation, such as 'Received forbidden error'. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Time (UTC) at which this event is generated. |
| Type | string | The name of the table |
