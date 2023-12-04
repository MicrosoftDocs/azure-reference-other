---
ms.service: azure-monitor
ms.topic: include
ms.date: 12/04/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: ACSEmailSendMailOperational
---


| Column | Type | Description |
|---|---|---|
| AttachmentsCount | int | The count of attachments attached to a request. |
| BccRecipientsCount | int | The count of unique recipients on the 'Bcc' line. |
| _BilledSize | real | The record size in bytes |
| Category | string | The log category of the event. Logs with the same log category and resource type will have the same properties fields. |
| CcRecipientsCount | int | The count of unique recipients on the 'Cc' line. |
| CorrelationId | string | The ID for correlated events. This value is populated with the MessageID returned by Email send requests and can be used to identify correlated events between Email Operational tables. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Location | string | The location the request was processed. |
| OperationName | string | The operation associated with log record. |
| OperationVersion | string | The API-version associated with the operation or version of the operation (if there is no API version). |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Size | real | The size of the email in megabypes. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| ToRecipientsCount | int | The count of unique recipients on the 'To' line. |
| TrafficSource | string | The traffic source of a request. |
| Type | string | The name of the table |
| UniqueRecipientsCount | int | The unique count of all recipients. |
