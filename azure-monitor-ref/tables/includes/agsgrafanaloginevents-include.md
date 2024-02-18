---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: AGSGrafanaLoginEvents
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Category | string | The category of the log record. |
| CorrelationId | string | GUID for the correlated logs. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Level | string | The severity level of the log record. |
| Location | string | The location (region) the Azure Managed Grafana instance was accessed in. |
| Message | string | The inner message of the log record. |
| OperationName | string | The Grafana operation associated with the log record. |
| ResourceGroup | string | The resource group containing the resource corresponding to the log record. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TargetResource | string | The corresponding resource name of the log record. |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (UTC) when the log record was generated. |
| TraceContext | dynamic | The W3C distributed tracing context for the log record. |
| Type | string | The name of the table |
| User | string | The user identity of the login event. |
| UserRole | string | The Grafana role of the user for the login event. |
