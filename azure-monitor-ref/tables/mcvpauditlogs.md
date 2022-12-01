---
title: Azure Monitor Logs reference - MCVPAuditLogs
description: Reference for MCVPAuditLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/1/2022
---

# MCVPAuditLogs

 The MCVP audit logs. This table will include audit logs for MCVP service transactions.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Microsoft Connected Vehicle Platform




## Columns

| Column | Type | Description |
| --- | --- | --- |
| CallerAccessLevels | string | The caller access level - Administrator, Writer or Reader. |
| CallerIdentities | string | The caller identity, user alias or email address. |
| CallerIpAddress | string | IPV4 caller ip address. |
| OperationAccessLevel | string | The operation access level of the request - Administrator, Writer or Reader. |
| OperationCategories | string | The operation request categories like Provision, Connection or Claims. |
| OperationCategoryDescription | string | The operation request category general description. |
| OperationName | string | The operation request name where the audit log was created. |
| OperationResult | string | The operation request result - Success or Fail. |
| OperationResultDescription | string | The operation request result description. The column will contain information if the OperationResult value is other than Success or Fail. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| SpanId | string | An identifier of the request as known by the caller. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Timestamp (in UTC) when the audit log was created. |
| TraceId | string | An identifier for distributed tracing through a system (W3C TraceContext). |
| Type | string | The name of the table |
