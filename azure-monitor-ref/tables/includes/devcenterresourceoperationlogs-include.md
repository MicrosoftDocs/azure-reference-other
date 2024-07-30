---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: DevCenterResourceOperationLogs
---


| Column | Type | Description |
|---|---|---|
| AdditionalProperties | dynamic | Property bag of dimensions that are useful for this entry. |
| _BilledSize | real | The record size in bytes |
| CorrelationId | string | ID which groups operation logs for ease of debugging. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Message | string | The log message which has details about the state of the resource. |
| OperationName | string | The operation stage of the service from which the log entry was generated. |
| Region | string | The region the resource is located in. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| SubResourceId | string | The resource within the DevCenter that this log relates to. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Time (UTC) when the log was created. |
| Type | string | The name of the table |
