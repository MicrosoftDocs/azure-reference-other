---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: AADCustomSecurityAttributeAuditLogs
---


| Column | Type | Description |
|---|---|---|
| AADOperationType | string | Type of the operation. Possible values are Add Update Delete and Other. |
| AADTenantId | string | ID of the AAD tenant. |
| ActivityDateTime | datetime | Date and time the activity was performed in UTC. |
| ActivityDisplayName | string | Activity name or the operation name. |
| AdditionalDetails | dynamic | Indicates additional details on the activity. Can have any string as a key or value. |
| _BilledSize | real | The record size in bytes |
| CallerIpAddress | string | IP address of caller. |
| CorrelationId | string | ID to provide audit trail. |
| DurationMs | long | The duration of the operation in milliseconds. |
| Id | string | Unique ID representing the audit activity. |
| Identity | string | The identity from the token that was presented when you made the request. It can be a user account, system account, or service principal. |
| InitiatedBy | dynamic | User or app initiated the activity. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Level | string | The severity level of the event. |
| Location | string | The region of the resource emitting the event. |
| LoggedByService | string | Service that initiated the activity. |
| OperationName | string | Name of the operation. |
| OperationVersion | string | The REST API version that's requested by the client. |
| Result | string | Result of the activity. Possible values are: success failure timeout unknownFutureValue. |
| ResultDescription | string | Provides the error description for the audit operation. |
| ResultReason | string | Describes cause of failure or timeout results. |
| ResultSignature | string | Contains the error code, if any, for the audit operation. |
| ResultType | string | The result of the audit operation can be Success or Failure. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| TargetResources | dynamic | Indicates information on which resource was changed due to the activity. |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The date and time of the event in UTC. |
| Type | string | The name of the table |
| UserAgent | string | User agent of initiator. |
