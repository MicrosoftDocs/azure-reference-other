---
title: Azure Monitor Logs reference - AEWComputePipelinesLogs
description: Reference for AEWComputePipelinesLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 1/28/2022
---

# AEWComputePipelinesLogs

 AEWComputePipelines Events for the Experiment Workspace.

## Categories

- Azure Resources
- Audit
## Solutions

- LogManagement
## Resource types

- Experiment Workspace




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AnalysisRequestId | string | The GUID of your analysisRequest in ExP pipeline. |
| AnalysisStudyId | string | The ID of your experiment study. |
| AnalysisTaskId | string | The ID of your experiment task. |
| AnalysisType | string | The type of your analysis. |
| Category | string | The event category. Typical log categories are Audit, Operational, Execution, and Request. |
| EventName | string | The event name. |
| ExpComponentName | string | The ExP component name of the events. |
| ExperimentationGroup | string | Experimentation group name of your experiment. |
| ExperimentId | string | The GUID of your experiment. |
| ExperimentStepId | string | The GUID of your experiment step. |
| ExPWorkspaceId | string | The Guid ID of your experimentation workspace. |
| Metrics | string | Event metrics in ExP Compute Pipeline with json format. |
| ProfileName | string | The name of your task profile. |
| Properties | string | Event properties in ExP Compute Pipeline with json format. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| StatusDescription | string | The status description of the event. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Time (UTC) of the HTTP request. |
| Type | string | The name of the table |
