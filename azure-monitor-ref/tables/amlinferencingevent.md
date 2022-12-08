---
title: Azure Monitor Logs reference - AmlInferencingEvent
description: Reference for AmlInferencingEvent table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/8/2022
---

# AmlInferencingEvent

 Events for inference or related operation on AKS or ACI compute type.

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
| AmlServiceName | string | The name of the AML service. |
| CorrelationId | string | A GUID used to group together a set of related events. |
| Identity | dynamic | The identity of the user or application that performed the operation. |
| Level | string | The severity level of the event. Must be one of Informational, Warning, Error, or Critical. |
| OperationName | string | The name of the operation associated with the log entry. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultType | string | The status of the event. Typical values include Started, In Progress, Succeeded, Failed, Active, and Resolved. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of the event. |
| Type | string | The name of the table |
