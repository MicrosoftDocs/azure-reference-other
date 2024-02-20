---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: AADDomainServicesDNSAuditsDynamicUpdates
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| BufferSize | int | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| EventType | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Name | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| operationName | string | Identifies the type of event emitted. |
| operationVersion | string | Version string.  Reserved. |
| RData | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| RecordId | string | Identifier for the underlying Windows event |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| resultDescription | string | Summary description of the event. |
| Source | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the event was generated. |
| Ttl | int | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| Type | string | The name of the table |
| Zone | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| ZoneScope | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
