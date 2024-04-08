---
ms.service: azure-monitor
ms.topic: include
ms.date: 04/08/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: NTAInsights
---


| Column | Type | Description |
|---|---|---|
| AdFlag | real | A ternary series containing (+1, -1, 0) marking up/down/no anomaly respectively. |
| AdScore | real | Anomaly score. |
| AggregationType | string | Type of data aggregation - 1 for short aggregation and 2 for long aggregation. |
| _BilledSize | real | The record size in bytes |
| DataPoints | string | Data points for aggregated data. |
| FlowStatus | string | The considered traffic is Allowed/Denied/All. |
| InsightsResourceId | string | Resource ID for the resource for which data is aggregated |
| IntervalEnd | datetime | End time of the data insights processing interval. |
| IntervalStart | datetime | Start time of the data insights processing interval. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Periodicity | real | The number of hours after whichthe data repeats itself. |
| PivotType | string | Pivot type for insights aggregation. |
| ProcessingTime | datetime | The time when periodicty is calculated. |
| Region | string | Region of Vnet flow logs. |
| SchemaVersion | string | Schema version. |
| SeriesNumber | real | An incremental value to represent the last aggregated series. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| SubType | string | Subtype for the insights logs. |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The time when the data gets ingested into the Log Analytics Workspace. |
| TrafficTime | datetime | Time when the anomaly has occured in data pattern. |
| TrafficVolumeActual | real | The actual traffic volume in the time period. |
| TrafficVolumeBaseline | real | The predicted value of the series, according to the decomposition per the anomaly calculation algorithm. |
| TrafficVolumeUnit | string | The aggregated values represent Flows/Bytes/Packets. |
| Type | string | The name of the table |
