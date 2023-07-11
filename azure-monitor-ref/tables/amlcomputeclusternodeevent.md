---
title: Azure Monitor Logs reference - AmlComputeClusterNodeEvent
description: Reference for AmlComputeClusterNodeEvent table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 7/10/2023
---

# AmlComputeClusterNodeEvent

 AmlCompute Cluster Node events

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Machine Learning




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real | The record size in bytes |
| ClusterCreationTime | string |  |
| ClusterName | string |  |
| InternalOperationName | string |  |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is *false* ingestion isn't billed to your Azure account |
| NodeAllocationTime | datetime |  |
| NodeBootTime | datetime |  |
| NodeId | string |  |
| Offer | string |  |
| OperationName | string |  |
| Publisher | string |  |
| ResizeEndTime | datetime |  |
| ResizeStartTime | datetime |  |
| ResultSignature | string |  |
| Sku | string |  |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| StartTaskEndTime | datetime |  |
| StartTaskStartTime | datetime |  |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime |  |
| TotalE2ETimeInSeconds | string |  |
| Type | string | The name of the table |
| Version | string |  |
| VmFamilyName | string |  |
| VmPriority | string |  |
| VmSize | string |  |
