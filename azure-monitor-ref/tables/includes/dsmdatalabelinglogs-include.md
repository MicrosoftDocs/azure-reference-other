---
ms.service: azure-monitor
ms.topic: include
ms.date: 08/08/2024
ms.author: orens
author: osalzberg
ms.custom: DSMDataLabelingLogs
---


| Column | Type | Description |
|---|---|---|
| AssetLastScanTime | datetime | The time (UTC) when the resource scan for sensitivity was performed by Azure Purview. |
| _BilledSize | real | The record size in bytes |
| CorrelationId | string | The ID that is used to correlate resource logs with data sensitivity logs. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| SensitivityLabelName | string | The name of sensitive label found and/or applied. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The time (UTC) when Azure Purview scan of asset occurred. |
| Type | string | The name of the table |
| Uri | string | Uniform resource identifier representing the resource that was scanned. |
