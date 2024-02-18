---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: ADPAudit
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| CorrelationId | string | Internal ADP correlation ID used in support scenarios. |
| Identity | dynamic | Active Directory identity claims |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Location | string | The location (region) of the resource. |
| OperationName | string | The operation associated with the log record. |
| OperationVersion | string | The API version against which the operation was performed. |
| Properties | dynamic | Additional properties related to the audit event. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultType | string | The result of the audit operation. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log record was generated. |
| TraceContext | dynamic | W3C Trace Context information used for event correlation. |
| Type | string | The name of the table |
