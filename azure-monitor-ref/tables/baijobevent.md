---
title: Azure Monitor Logs reference - BaiJobEvent
description: Reference for BaiJobEvent table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/13/2023
---

# BaiJobEvent

 BatchAI Job events

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Machine Learning




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real |  |
| ClusterId | string |  |
| ClusterName | string |  |
| ClusterResourceGroupName | string |  |
| CreationApiVersion | string |  |
| CustomerSubscriptionId | string |  |
| ErrorDetails | string |  |
| EventType | string |  |
| ExecutionState | string |  |
| ExperimentId | string |  |
| ExperimentName | string |  |
| InternalOperationName | string |  |
| _IsBillable | string |  |
| JobErrorMessage | string |  |
| JobId | string |  |
| JobName | string |  |
| NodeId | string |  |
| OperationName | string |  |
| ProvisioningState | string |  |
| ResourceGroupName | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultSignature | string |  |
| RunInContainer | string |  |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TFParameterServerCount | string |  |
| TFWorkerCount | string |  |
| TimeGenerated | datetime |  |
| ToolType | string |  |
| Type | string | The name of the table |
| WorkspaceName | string |  |
