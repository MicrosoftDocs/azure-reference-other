---
title: Azure Monitor Logs reference - SynapseIntegrationActivityRuns
description: Reference for SynapseIntegrationActivityRuns table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
---

# SynapseIntegrationActivityRuns

 Logs for Synapse integration activity runs.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Synapse Workspaces




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ActivityName | string | The name of the activity run. |
| ActivityRunId | string | The run id of the activity run. |
| ActivityType | string | The type of the activity run. |
| Annotations | dynamic | The annotation details of the log record. |
| _BilledSize | real |  |
| Category | string | The category of the log. |
| CorrelationId | string | The correlationId for the log record. |
| EffectiveIntegrationRuntime | string | The effective integration runtime the activity run job. |
| End | datetime | The end time (UTC) for the activity run. |
| _IsBillable | string |  |
| Level | string | The log type info level of the record. |
| Location | string | The location of the resource in the cloud where this log is originated. |
| OperationName | string | The operation associated with log record. |
| PipelineName | string | The pipeline name of the activity flow. |
| PipelineRunId | string | The pipeline runId of the activity flow. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| Start | datetime | The start time (UTC) of the activity run. |
| Status | string | The Status of the sql requests. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| Tags | dynamic | The associated tags of the log record. |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
| UserProperties | dynamic | The user properties of the log record. |
