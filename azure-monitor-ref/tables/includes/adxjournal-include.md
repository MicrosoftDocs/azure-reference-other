---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: ADXJournal
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| ChangeCommand | string | The executed control command that triggered the metadata change |
| CorrelationId | string | The client request ID |
| DatabaseName | string | The name of the database changed following the event |
| EntityContainerName | string | The entity container name (entity=column, container=table), or the database name |
| EntityName | string | The entity name that the operation was executed on, before the change |
| EntityVersion | string | The new metadata version (DB/cluster) following the change |
| Event | string | The metadata change event name |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| OperationTimestamp | datetime | The timestamp (UTC) at which the metadata operation completed |
| OriginalEntityState | string | The state of the entity (entity properties) before the change |
| OriginalEntityVersion | string | The version of the entity (entity properties) before the change |
| Principal | string | The principal (user/app) that executed the control command |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RootActivityId | string | The root activity ID of the operation that caused the metadata change (for example: 1234ab0c-567d-8c9e-0123-456789fg012h) |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The time (UTC) at which this log was sent to Log Analytics |
| Type | string | The name of the table |
| UpdatedEntityName | string | The new entity name after the change |
| UpdatedEntityState | string | The new state after the change |
| User | string | The user that executed the control command |
