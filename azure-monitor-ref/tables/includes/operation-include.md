---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: Operation
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Computer | string | Name of a physical or virtual machine having membership with Log Analytics agent. |
| CorrelationId | string | GUID that is shared with telemetry belonging to the same uber action. |
| Detail | string | User friendly string that describes further details about the operation |
| ErrorId | string | Deprecated. |
| HelpLink | string | Reference URL for additional contextual information. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| ManagementGroupName | string | Name of the Operations Manager management group for System Center Operations Manager agents. |
| OperationCategory | string | Name of the area that produced the record. |
| OperationKey | string | Operation ID. Can be a GUID or string. |
| OperationStatus | string | Operation status description. Ccommon values include Warning Succeeded Failed Error. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Solution | string | Name of the managed solution that produced the record. Can also include other sources such as RestAPI. |
| SourceComputerId | string | Unique GUID identifier for a computer. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime | Date and time that the record was created. |
| Type | string | The name of the table |
