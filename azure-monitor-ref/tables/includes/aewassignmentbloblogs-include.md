---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: AEWAssignmentBlobLogs
---


| Column | Type | Description |
|---|---|---|
| AssignmentBlobDataVersion | int | Data version (gets incremented with every experiment operation) of Assignment Blob. |
| AssignmentBlobLastOperationId | string | The last operation id that got published for an assignment blob data version which is generally one below the current version. |
| AssignmentBlobNewOperationIds | dynamic | List of new operation ids (changes) that are getting published or added with this assignment blob. |
| AssignmentBlobSchemaVersion | string | Schema version of assignment blob data associated with this operation. |
| _BilledSize | real | The record size in bytes |
| CorrelationId | string | The ID for correlated events. Can be used to identify correlated events between multiple tables. |
| DurationMs | int | The duration of the operation (to upload blob file) in milliseconds. |
| ExperimentWorkspaceId | string | The Guid of your experimentation workspace. |
| HttpStatusCode | int | The HTTP status code of the corresponding REST API call operation. |
| Identity | string | The resource id of the user assigned managed identity that performed this operation. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Level | string | The severity level of the operation. Will be one of Information, Warning, Error, or Critical. |
| Location | string | The location of the resource. |
| OperationName | string | The operation associated with log record. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultDescription | string | The static text description of this operation. |
| ResultType | string | The status of the event. Typical values include Succeeded, Failed. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
| URI | string | The request Url. |
