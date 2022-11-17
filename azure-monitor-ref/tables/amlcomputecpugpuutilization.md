---
title: Azure Monitor Logs reference - AmlComputeCpuGpuUtilization
description: Reference for AmlComputeCpuGpuUtilization table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
---

# AmlComputeCpuGpuUtilization

 Azure Machine Learning services CPU and GPU utilizaion logs.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Machine Learning




## Columns

| Column | Type | Description |
| --- | --- | --- |
| CallerIpAddress | string | The caller IP address. |
| CorrelationId | string | A GUID used to group together a set of related events. |
| DeviceId | string | DeviceId of GPU. |
| DeviceType | string | Type of compute, either CPU or GPU. |
| DurationMs | string | The duration of the operation in milliseconds. |
| Identity | string | Identity of the user or application that performed the operation. |
| Level | string | The severity level of the event. Must be one of Informational, Warning, Error, or Critical. |
| Location | string | The region of the resource emitting the event. |
| NodeId | string | NodeId on the cluster. |
| OperationName | string | The name of the operation associated with the log entry. |
| OperationVersion | string | The api-version associated with the operation, if the operationName was performed using an API. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultDescription | string | The static text description of this operation. |
| ResultSignature | string | The sub status of the event. If this operation corresponds to a REST API call, this is the HTTP status code of the corresponding REST call. |
| ResultType | string | The status of the event. Typical values include Started, In Progress, Succeeded, Failed, Active, and Resolved. |
| RunId | string | Unique run identifier. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of the event. |
| Type | string | The name of the table |
| Utilization | string | Compute utilization of node. |
| WorkspaceId | string | Unique workspace identifer. |
| WorkspaceName | string | User friendly workspace identifier. |
