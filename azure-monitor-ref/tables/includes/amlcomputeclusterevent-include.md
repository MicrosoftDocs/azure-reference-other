---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: AmlComputeClusterEvent
---


| Column | Type | Description |
|---|---|---|
| AllocationState | string |   |
| AllocationStateTransitionTime | datetime |   |
| _BilledSize | real | The record size in bytes |
| ClusterErrorCodes | string |   |
| ClusterName | string |   |
| ClusterType | string |   |
| CoreCount | int |   |
| CreatedBy | string |   |
| CreationApiVersion | string |   |
| CurrentNodeCount | int |   |
| EventType | string |   |
| IdleNodeCount | int |   |
| InitialNodeCount | int |   |
| InternalOperationName | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| IsResizeGrow | string |   |
| LeavingNodeCount | int |   |
| MaximumNodeCount | int |   |
| MinimumNodeCount | int |   |
| NodeDeallocationOption | string |   |
| NodeIdleTimeSecondsBeforeScaleDown | int |   |
| Offer | string |   |
| OperationName | string |   |
| PreemptedNodeCount | string |   |
| PreparingNodeCount | int |   |
| ProvisioningState | string |   |
| Publisher | string |   |
| QuotaAllocated | string |   |
| QuotaUtilized | string |   |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultSignature | string |   |
| RunningNodeCount | int |   |
| ScalingType | string |   |
| Sku | string |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| SubnetId | string |   |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TargetNodeCount | int |   |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
| UnusableNodeCount | int |   |
| Version | string |   |
| VmFamilyName | string |   |
| VmPriority | string |   |
| VmSize | string |   |
