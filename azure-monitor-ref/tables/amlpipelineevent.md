---
title: Azure Monitor Logs reference - AmlPipelineEvent
description: Reference for AmlPipelineEvent table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# AmlPipelineEvent

 Events when ML pipeline draft or endpoint or module are accessed (read, created, or deleted).

## Categories

- Azure Resources
- Audit
## Solutions

- LogManagement
## Resource types

- Machine Learning




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AadTenantId | string | The AAD tenant ID the operation was submitted for. |
| AmlModuleId | string | The unique ID of the module. |
| AmlModuleName | string | The name of the AML Module. |
| AmlParentPipelineId | string | The ID of the parent AML pipeline (in the case of cloning). |
| AmlPipelineDraftId | string | The ID of the AML pipeline draft. |
| AmlPipelineDraftName | string | The name of the AML pipeline draft. |
| AmlPipelineEndpointId | string | The ID of the AML pipeline endpoint. |
| AmlPipelineEndpointName | string | The name of the AML pipeline endpoint. |
| AmlPipelineId | string | The ID of the AML pipeline. |
| AmlWorkspaceId | string | The unique ID of the AML workspace. |
| AmlWorkspaceName | string | The name of the AML workspace. |
| CorrelationId | string | A GUID used to group together a set of related events. |
| Identity | dynamic | The identity of the user or application that performed the operation. |
| OperationName | string | The name of the operation associated with the log entry. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultType | string | The status of the event. Typical values include Started, In Progress, Succeeded, Failed, Active, and Resolved. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of the event. |
| Type | string | The name of the table |
