---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: ResourceManagementPublicAccessLogs
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| CallerIpAddress | string | Client IP address. |
| Category | string | A category type associated with the operation. |
| CorrelationId | string | An event ID that can be used to correlated events between multiple tables. |
| DurationMs | long | Amount of time (in milliseconds) taken by the operation. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| ObjectIdentifier | string | Object ID for the caller of the operation. |
| OperationName | string | The operation associated with the log record. |
| OperationType | string | The resource type and operation associated with the log record. |
| OperationVersion | string | An API version associated with the operation. |
| PrivateLinkAssociationIds | dynamic | List of private link association resource IDs present at the scope. |
| ProviderName | string | The resource provider name associated with the log record. |
| ResultSignature | int | Status code of the operation. It covers success and failure. |
| ResultType | string | Status of the operation. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log entry was generated. |
| Type | string | The name of the table |
| Uri | string | The resource URI for the operation. |
