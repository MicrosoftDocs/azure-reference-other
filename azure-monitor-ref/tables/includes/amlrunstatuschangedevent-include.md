---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: AmlRunStatusChangedEvent
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| CallerIpAddress | string | The caller IP address. |
| CorrelationId | string | A GUID used to group together a set of related events. |
| DurationMs | string | The duration of the operation in milliseconds. |
| Identity | string | Identity of the user or application that performed the operation |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Level | string | The severity level of the event. Must be one of Informational, Warning, Error, or Critical. |
| Location | string | The region of the resource emitting the event. |
| Message | string | Message associated with run status change. |
| OperationName | string | The name of the operation associated with the log entry. |
| OperationVersion | string | The api-version associated with the operation, if the operationName was performed using an API. |
| ParentRunId | string | The unique identifier for the parent run. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultDescription | string | The static text description of this operation. |
| ResultSignature | string | The sub status of the event. If this operation corresponds to a REST API call, this is the HTTP status code of the corresponding REST call. |
| ResultType | string | The status of the event. Typical values include Started, In Progress, Succeeded, Failed, Active, and Resolved. |
| RootRunId | string | The unique identifier for the root run. |
| RunId | string | Unique run identifier. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| Status | string | Updated run status. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of the event. |
| TriggeringUserName | string | Friendly name of run status change initiator. |
| Type | string | The name of the table |
| WorkspaceId | string | Unique workspace identifer. |
| WorkspaceName | string | User friendly workspace identifier. |
