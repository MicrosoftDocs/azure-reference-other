---
title: Azure Monitor Logs reference - ADFSandboxPipelineRun
description: Reference for ADFSandboxPipelineRun table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/13/2023
---

# ADFSandboxPipelineRun

 

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Data factories




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Annotations | string |  |
| _BilledSize | real |  |
| Category | string |  |
| CorrelationId | string |  |
| End | datetime |  |
| ErrorCode | string |  |
| ErrorMessage | string |  |
| EventMessage | string |  |
| FailureType | string |  |
| Input | string |  |
| _IsBillable | string |  |
| Level | string |  |
| Location | string |  |
| OperationName | string |  |
| Output | string |  |
| Parameters | string |  |
| PipelineName | string |  |
| Predecessors | string |  |
| ResourceId | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RunId | string |  |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| Start | datetime |  |
| Status | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| SystemParameters | string |  |
| Tags | string |  |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
| UserProperties | string |  |
