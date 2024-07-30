---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: MCVPAuditLogs
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| CallerAccessLevels | string | The caller access level - Administrator, Writer or Reader. |
| CallerIdentities | string | The caller identity, user alias or email address. |
| CallerIpAddress | string | IPV4 caller ip address. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| OperationAccessLevel | string | The operation access level of the request - Administrator, Writer or Reader. |
| OperationCategories | string | The operation request categories like Provision, Connection or Claims. |
| OperationCategoryDescription | string | The operation request category general description. |
| OperationName | string | The operation request name where the audit log was created. |
| OperationResult | string | The operation request result - Success or Fail. |
| OperationResultDescription | string | The operation request result description. The column will contain information if the OperationResult value is other than Success or Fail. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| SpanId | string | An identifier of the request as known by the caller. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (in UTC) when the audit log was created. |
| TraceId | string | An identifier for distributed tracing through a system (W3C TraceContext). |
| Type | string | The name of the table |
