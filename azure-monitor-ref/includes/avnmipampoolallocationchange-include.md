---
ms.service: azure-monitor
ms.topic: include
ms.date: 12/04/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: AVNMIPAMPoolAllocationChange
---


| Column | Type | Description |
|---|---|---|
| AllocationResources | dynamic | Details about resources allocated to the pool that changed, including the resource id, cidrs, and compliancy. |
| _BilledSize | real | The record size in bytes |
| ChangeReason | string | The reason why allocations were changed and can include: ResourceAddedToPool, ResourceRemovedFromPool, ResourceDeleted, ResourceCidrsChanged, ReservedResourceCreated, AvnmScopeChanged. |
| ChangeType | string | The type of allocation change and can include: Add, Remove, Update. |
| CorrelationId | string | The correlation ID associated with the pool allocation change operation. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Location | string | Region of the IPAM Pool. |
| LogLevel | string | Indicates the log level and can include: Info, Warning, Error. |
| Message | string | A brief success or failure message. |
| OperationName | string |  Name of the operation that triggered the pool allocation change. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultType | string | Indicates the operation status and can include: Success, Failure. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime |  The date and time the event was generated. |
| Type | string | The name of the table |
