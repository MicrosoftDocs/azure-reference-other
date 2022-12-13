---
title: Azure Monitor Logs reference - ADPAudit
description: Reference for ADPAudit table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/8/2022
---

# ADPAudit

 Audit entries for ADP operations.

## Categories

- Azure Resources
- Audit
## Solutions

- LogManagement
## Resource types

- Azure Autonomous Development Platform workspace




## Columns

| Column | Type | Description |
| --- | --- | --- |
| CorrelationId | string | Internal ADP correlation ID used in support scenarios. |
| Identity | dynamic | Active Directory identity claims |
| Location | string | The location (region) of the resource. |
| OperationName | string | The operation associated with the log record. |
| OperationVersion | string | The API version against which the operation was performed. |
| Properties | dynamic | Additional properties related to the audit event. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultType | string | The result of the audit operation. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log record was generated. |
| TraceContext | dynamic | W3C Trace Context information used for event correlation. |
| Type | string | The name of the table |
