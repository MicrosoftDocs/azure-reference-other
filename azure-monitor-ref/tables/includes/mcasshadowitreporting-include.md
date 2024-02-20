---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: McasShadowItReporting
---


| Column | Type | Description |
|---|---|---|
| AadTenantId | string |   |
| AppCategory | string |   |
| AppId | string |   |
| AppInstance | string |   |
| AppName | string |   |
| AppScore | int |   |
| AppTags | dynamic |   |
| _BilledSize | real | The record size in bytes |
| BlockedEvents | int |   |
| Date | datetime |   |
| DownloadedBytes | int |   |
| EnrichedUserName | string |   |
| IpAddress | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| MachineId | string |   |
| MachineName | string |   |
| RawUserName | string |   |
| RichUserName | string |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| StreamName | string |   |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime |   |
| TotalBytes | int |   |
| TotalEvents | int |   |
| Type | string | The name of the table |
| UploadedBytes | int |   |
| UserName | string |   |
