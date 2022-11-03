---
title: Azure Monitor Logs reference - SynapseIntegrationTriggerRuns
description: Reference for SynapseIntegrationTriggerRuns table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# SynapseIntegrationTriggerRuns

 Logs for Synapse integration trigger runs.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Synapse Workspaces




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Annotations | dynamic | The annotation details of the log record. |
| Category | string | The category of the log. |
| CorrelationId | string | The correlationId for the log record. |
| Level | string | The log type info level of the record. |
| Location | string | The location of the resource in the cloud where this log is originated. |
| OperationName | string | The operation associated with log record. |
| Parameters | dynamic | The parameter details of the pipeline run. |
| PipelineTenantId | string | The tenantId details of the pipeline run. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| Start | datetime | The start time (UTC) of the trigger run. |
| Status | string | The Status of the SQL requests. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| SystemParameters | dynamic | The system parameter details of the pipeline run. |
| Tags | dynamic | The associated tags of the log record. |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| TriggerEvent | string | The trigger id of the log record. |
| TriggerId | string | The trigger id of the log record. |
| TriggerName | string | The trigger name of the log record. |
| TriggerType | string | The trigger type of the log record. |
| Type | string | The type of the pipeline run. |
| UserProperties | dynamic | The user properties of the log record. |
