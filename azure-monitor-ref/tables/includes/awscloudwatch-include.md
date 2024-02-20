---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: AWSCloudWatch
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| ExtractedTime | datetime | The timestamp (UTC) of when the event was generated. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Message | string | The data contained within logs from CloudWatch. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) when the event was generated and equals to 'ExtractedTime' when included in message. If timestamp is missing, it’s set to the ingestion time. |
| Type | string | The name of the table |
