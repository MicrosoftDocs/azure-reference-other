---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: AgriFoodJobProcessedLogs
---


| Column | Type | Description |
|---|---|---|
| ApplicationId | string | ApplicationId in identity claims. |
| _BilledSize | real | The record size in bytes |
| Category | string | Logs generated as a result of operations executed using FarmBeats APIs are grouped into categories. Categories in FarmBeats are logical groupings based on either the data source the underlying APIs fetch data from or on the basis of hierarchy of entities in FarmBeats. |
| ClientTenantId | string | TenantId in identity claims. |
| CorrelationId | string | Unique identifier to be used to correlate logs, when available. |
| DurationMs | real | Time it took to service the REST API request, in milliseconds. |
| FarmerId | string | Farmer ID associated with the request, wherever applicable. |
| InitiatedBy | string | Indicates whether the job was initiated by FarmBeats or user. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| JobId | string | User defined ID of the job. |
| JobRunType | string | Indicates whether a job is a periodic job or a one-time job. |
| Level | string | The severity level of the event, will be one of Informational, Warning, Error, or Critical. |
| Location | string | The region of the resource emitting the event. |
| ObjectId | string | ObjectId in identity claims. |
| OperationName | string | The operation name for which the log entry was created. |
| Properties | dynamic | Additional properties associated with the Job. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultDescription | string | Additional details about the result, when available. |
| ResultType | string | Result of the REST API request. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (in UTC) when the log was created. |
| Type | string | The name of the table |
