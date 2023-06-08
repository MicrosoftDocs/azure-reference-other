---
title: Azure Monitor Logs reference - AmlDataLabelEvent
description: Reference for AmlDataLabelEvent table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
---

# AmlDataLabelEvent

 Events when data label(s) or its projects is accessed (read, created, or deleted).

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
| AmlDataStoreName | string | The name of the data store where the project's data is stored. |
| AmlLabelNames | string | The label class names which are created for the project. |
| AmlProjectId | string | The unique identifier of the project. |
| AmlProjectName | string | The name of the AML project. |
| _BilledSize | real |  |
| CorrelationId | string | A GUID used to group together a set of related events. |
| Identity | dynamic | The identity of the user or application that performed the operation. |
| _IsBillable | string |  |
| Level | string | The severity level of the event. Must be one of Informational, Warning, Error, or Critical. |
| OperationName | string | The name of the operation associated with the log entry. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultType | string | The status of the event. Typical values include Started, In Progress, Succeeded, Failed, Active, and Resolved. |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of the event. |
| Type | string | The name of the table |
