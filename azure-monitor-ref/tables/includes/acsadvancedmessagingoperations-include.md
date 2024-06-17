---
ms.service: azure-monitor
ms.topic: include
ms.date: 06/17/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: ACSAdvancedMessagingOperations
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| CallerIpAddress | string | The caller IP address, if the operation corresponds to an API call that would come from an entity with a publicly available IP address. |
| Category | string | The log category of the event. Logs with the same log category and resource type will have the same properties fields. |
| ChannelId | string | The Channel Registration ID of the channel used to send the request. |
| CorrelationId | string | The ID for correlated events. Can be used to identify correlated events between multiple tables. |
| DurationMs | int | The duration of the operation in milliseconds. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Level | string | The severity level of the operation. |
| Location | string | The location the request was processed. |
| MessageStatus | string | The status result of the message send. Possible values include: "delivered", "read", "sent", "failed", "accepted", "preprocessingfailed", "received", and "unknown". |
| MessageType | string | The type of message in the request. Possible values include: "text", "media", and "template". |
| OperationName | string | The operation associated with log record. |
| OperationVersion | string | The API-version associated with the operation or version of the operation (if there is no API version). |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultDescription | string | The static text description of this operation. |
| ResultSignature | string | The sub status of the operation. If this operation corresponds to a REST API call, this field is the HTTP status code of the corresponding REST call. |
| ResultType | string | The status of the operation. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
| URI | string | The URI of the request. |
