---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: AADDomainServicesAccountLogon
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Category | string |   |
| CertIssuerName | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| CertSerialNumber | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| CertThumbprint | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| ClientUserName | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| CorrelationId | string |   |
| FailureCode | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| IpAddress | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| IpPort | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| MappedName | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| MappingBy | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| OperationName | string |   |
| PackageName | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| PreAuthType | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| RecordId | string | A unique identifier corresponding to this record. |
| ResourceId | string |   |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultDescription | string |   |
| ResultType | string |   |
| ServiceName | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TicketOptions | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
