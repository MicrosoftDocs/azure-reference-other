---
title: Azure Monitor Logs reference - ADPDiagnostics
description: Reference for ADPDiagnostics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/8/2022
---

# ADPDiagnostics

 Diagnostic logs of the ADP service.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Azure Autonomous Development Platform workspace




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Category | string | The category of the diagnostic log record. |
| CorrelationId | string | Internal ADP correlation ID used in support scenarios. |
| Level | string | The verbosity level of the log record ('Informational', 'Warning', 'Error', or 'Critical'). |
| Location | string | The location (region) of the resource. |
| Message | string | The log record message. |
| OperationName | string | The operation associated with the log record. |
| OperationVersion | string | The API version against which the operation was performed. |
| Properties | dynamic | Additional properties related to the diagnostic log record. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log record was generated. |
| TraceContext | dynamic | W3C Trace Context information used for event correlation. |
| Type | string | The name of the table |
