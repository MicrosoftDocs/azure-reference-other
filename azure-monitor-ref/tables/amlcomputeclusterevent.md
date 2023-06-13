---
title: Azure Monitor Logs reference - AmlComputeClusterEvent
description: Reference for AmlComputeClusterEvent table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/13/2023
---

# AmlComputeClusterEvent

 AmlCompute Cluster events

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Machine Learning




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AllocationState | string |  |
| AllocationStateTransitionTime | datetime |  |
| _BilledSize | real |  |
| ClusterErrorCodes | string |  |
| ClusterName | string |  |
| ClusterType | string |  |
| CoreCount | int |  |
| CreatedBy | string |  |
| CreationApiVersion | string |  |
| CurrentNodeCount | int |  |
| EventType | string |  |
| IdleNodeCount | int |  |
| InitialNodeCount | int |  |
| InternalOperationName | string |  |
| _IsBillable | string |  |
| IsResizeGrow | string |  |
| LeavingNodeCount | int |  |
| MaximumNodeCount | int |  |
| MinimumNodeCount | int |  |
| NodeDeallocationOption | string |  |
| NodeIdleTimeSecondsBeforeScaleDown | int |  |
| Offer | string |  |
| OperationName | string |  |
| PreemptedNodeCount | string |  |
| PreparingNodeCount | int |  |
| ProvisioningState | string |  |
| Publisher | string |  |
| QuotaAllocated | string |  |
| QuotaUtilized | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultSignature | string |  |
| RunningNodeCount | int |  |
| ScalingType | string |  |
| Sku | string |  |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| SubnetId | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TargetNodeCount | int |  |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
| UnusableNodeCount | int |  |
| Version | string |  |
| VmFamilyName | string |  |
| VmPriority | string |  |
| VmSize | string |  |
