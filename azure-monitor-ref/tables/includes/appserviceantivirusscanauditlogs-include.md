---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: AppServiceAntivirusScanAuditLogs
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Category | string | Log category name |
| ErrorMessage | string | Error Message |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| ListOfInfectedFiles | string | List of each virus file path |
| NumberOfInfectedFiles | int | Total number of files infected with virus |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ScanStatus | string | Status of the scan |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Time when event is generated |
| TimeStamp | datetime | Time when event is generated |
| TotalFilesScanned | int | Total number of scanned files |
| Type | string | The name of the table |
