---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/05/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: AMWMetricsUsageDetails
---


| Column | Type | Description |
|---|---|---|
| AMWResourceName | string | Azure Monitor Workspace resource name. |
| _BilledSize | real | The record size in bytes |
| DailyTimeseriesCount | long | Daily timeseries count associated with the labels/dimensions for the metric. |
| DaysSinceMetricQueried | int | Number of days from the specified date range when the metric was queried last. |
| DimensionsList | string | The set of labels/dimensions being described. |
| EndTime | datetime | The end time (UTC) of the date range being described. |
| IncomingEventsCount | long | Number of events received for the specified date range. |
| IngestedSamplesCount | long | Number of samples ingested in the specified date range. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| MetricName | string | The name of the metric the insights is generated for. |
| MetricNamespace | string | Namespace in the Azure Monitor Workspace the metric belongs to. |
| NumberOfQueries | int | Number of queries received for the specified date range. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| StartTime | datetime | The start time (UTC) of the date range being described. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) when the summary data for the row was produced. |
| Type | string | The name of the table |
