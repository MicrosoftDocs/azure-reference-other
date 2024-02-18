---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: AzureMetricsV2
---


| Column | Type | Description |
|---|---|---|
| Average | real | Average value collected during in the time range. |
| _BilledSize | real | The record size in bytes |
| Count | real | Number of samples collected during the time range. |
| Dimension | dynamic | Associated dimension of the metric in JSON format. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Maximum | real | Maximum value collected during in the time range. |
| MetricCategory | string | Category name of the metric. |
| MetricName | string | Display name of the metric. |
| MetricResourceType | string | Resource type of the Azure resource reporting the metric. |
| Minimum | real | Minimum value collected during in the time range. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (UTC) when the record was generated. |
| TimeGrain | string | Time grain of the metric. |
| Total | real | Sum of all of the values in the time range. |
| Type | string | The name of the table |
| UnitName | string | Unit of the metric. |
