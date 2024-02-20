---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: AHDSDicomDiagnosticLogs
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| CorrelationId | string | An identifier used to group together a set of related events. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Location | string | Azure region of service from which log was generated. Examples are 'eastus', 'centralindia', 'westus2', etc. |
| LogLevel | string | The log's severity level. Possible values are Informational, Warning, and Error. |
| Message | string | Description of the log entry. |
| OperationName | string | The operation name for which the log entry was generated. For example, Store/PostInstance/POST |
| Properties | dynamic | Additional information about the event in JSON array format. Examples include DICOM identifiers present in the request. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Time (UTC) when the log was created. |
| Type | string | The name of the table |
