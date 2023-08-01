---
title: Azure Monitor Logs reference - AFSAuditLogs
description: Reference for AFSAuditLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/31/2023
---

# AFSAuditLogs

 This table contains audit logs retrieved from your Azure Managed Lustre filesystem resource. These logs capture all priviledged operations performed on each Azure Managed Lustre resource. They can be used to monitor events and configure alerts on your resource.

## Categories

- Audit
- Azure Resources
## Solutions

- LogManagement
## Resource types

- Azure Managed Lustre




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ActivityId | string | Internal identifier used for tracking. |
| _BilledSize | real | The record size in bytes |
| Identity | dynamic | JSON structure that describes the identity of the user or application that performed the operation. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is *false* ingestion isn't billed to your Azure account |
| Location | string | The region of the resource associated with the event. |
| OperationName | string | The operation name for which the log entry was created. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultDescription | string | Details about the result of the operation, if available. |
| ResultSignature | int | HTTP status of API request. |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (UTC) when the log was created. |
| Type | string | The name of the table |
