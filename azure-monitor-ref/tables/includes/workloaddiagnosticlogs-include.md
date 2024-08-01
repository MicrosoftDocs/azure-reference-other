---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: WorkloadDiagnosticLogs
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Category | string | The category of the log. |
| Computer | string | Name of the Computer generating the log. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Message | string | The message of the log entry. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| Status | string | The status of the record. Example: Error, Warning, etc. |
| Tags | dynamic | Dimensions or other metatata about the record. For example may contain the Monitoring profile ID the log entry is about. |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp of when the log was generated. |
| Type | string | The name of the table |
