---
title: Azure Monitor Logs reference - LogicAppWorkflowRuntime
description: Reference for LogicAppWorkflowRuntime table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/2/2023
---

# LogicAppWorkflowRuntime

 Logs generated during Logic Apps workflow runtime.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- App Services




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ActionName | string | The name of the workflow action. |
| ActionTrackingId | string | The unique ID of the workflow action. |
| ClientKeywords | string | The client keywords sent through the header. |
| ClientTrackingId | string | The unique ID of the client. |
| Code | string | The HTTP status code of the request. |
| EndTime | datetime | The end time (UTC) of the operation. |
| Error | string | The error message of this operation. |
| Location | string | The geographical run location of the workflow. |
| OperationName | string | The name of this operation. |
| OriginRunId | string | The unique ID of the original workflow run, only relevant for resubmission scenarios. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RetryHistory | string | The retry history of the workflow action. |
| RunId | string | The unique ID of the workflow run. |
| SourceSystem | string |  |
| StartTime | datetime | The start time (UTC) of the operation. |
| Status | string | The status of the operation, e.g. Succeeded, Failed, Skipped, Ignored. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| Tags | string | The custom tags associated with the workflow. |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| TrackedProperties | string | The custom tracked properties. |
| TriggerName | string | The name of the workflow trigger. |
| Type | string | The name of the table |
| WorkflowId | string | The unique ID of the workflow. |
| WorkflowName | string | The name of the workflow. |
