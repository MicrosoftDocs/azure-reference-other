---
title: Azure Monitor Logs reference - BaiJobEvent
description: Reference for BaiJobEvent table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/1/2022
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
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TFParameterServerCount | string |  |
| TFWorkerCount | string |  |
| TimeGenerated | datetime |  |
| ToolType | string |  |
| Type | string | The name of the table |
| WorkspaceName | string |  |
