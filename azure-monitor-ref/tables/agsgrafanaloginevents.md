---
title: Azure Monitor Logs reference - AGSGrafanaLoginEvents
description: Reference for AGSGrafanaLoginEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# AGSGrafanaLoginEvents

 Login events for an instance of Azure Managed Workspace for Grafana including user identity, user Grafana role (in success) and detailed message (in failure).

## Categories

- Azure Resources
- Audit
## Solutions

- LogManagement
## Resource types

- Azure Managed Workspace for Grafana




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Category | string | The category of the log record. |
| CorrelationId | string | GUID for the correlated logs. |
| Level | string | The severity level of the log record. |
| Location | string | The location (region) the Azure Managed Grafana instance was accessed in. |
| Message | string | The inner message of the log record. |
| OperationName | string | The Grafana operation associated with the log record. |
| ResourceGroup | string | The resource group containing the resource corresponding to the log record. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TargetResource | string | The corresponding resource name of the log record. |
| TenantId | string |  |
| TimeGenerated | datetime | Timestamp (UTC) when the log record was generated. |
| TraceContext | dynamic | The W3C distributed tracing context for the log record. |
| Type | string | The name of the table |
| User | string | The user identity of the login event. |
| UserRole | string | The Grafana role of the user for the login event. |
