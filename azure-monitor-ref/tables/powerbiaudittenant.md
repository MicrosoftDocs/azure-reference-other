---
title: Azure Monitor Logs reference - PowerBIAuditTenant
description: Reference for PowerBIAuditTenant table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/1/2022
---

# PowerBIAuditTenant

 Contains Power BI audit events as per the Activity Log and Office365 Audit Log. Covers operations over full lifecycle of Power BI assets such as creation, modification and deletion.

## Categories

- Azure Resources
- Audit
## Solutions

- LogManagement
## Resource types

- Power BI Datasets




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AuditData | string | The complete audit record containing relevant operation details such as workspace name or dataset name. |
| CorrelationId | string | An event ID that can be used to correlated events between multiple tables. |
| CustomerTenantId | string | Customer's Power BI tenant identifier. |
| ExecutingUser | string | The user executing the operation. |
| Level | string | Contains the severity level of the operation being logged. Success, Informational, Warning, or Error. |
| LogAnalyticsCategory | string | Unique category of the events like like Audit/Security/Request. |
| OperationName | string | The operation associated with the log record. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp(UTC) of when the log entry was generated. |
| Type | string | The name of the table |
