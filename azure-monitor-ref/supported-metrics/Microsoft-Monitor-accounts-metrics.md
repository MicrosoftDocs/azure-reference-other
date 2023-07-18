---
title: Supported metrics - Microsoft.Monitor/accounts
description: Reference for Microsoft.Monitor/accounts metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Monitor/accounts  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Monitor/accounts resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Active Time Series<p><p> The number of unique time series recently ingested into the account over the previous 12 hours |`ActiveTimeSeries` |Count |Maximum |StampColor |No|
|Active Time Series Limit<p><p>The limit on the number of unique time series which can be actively ingested into the account |`ActiveTimeSeriesLimit` |Count |Maximum |StampColor |No|
| Active Time Series % Utilization<p><p>The percentage of current active time series account limit being utilized |`ActiveTimeSeriesPercentUtilization` |Percent |Average |StampColor |No|
|Events Per Minute Ingested<p><p>The number of events per minute recently received |`EventsPerMinuteIngested` |Count |Maximum |StampColor |No|
|Events Per Minute Ingested Limit<p><p>The maximum number of events per minute which can be received before events become throttled |`EventsPerMinuteIngestedLimit` |Count |Maximum |StampColor |No|
|Events Per Minute Ingested % Utilization<p><p>The percentage of the current metric ingestion rate limit being utilized |`EventsPerMinuteIngestedPercentUtilization` |Percent |Average |StampColor |No|
|Simple Data Samples Stored<p><p>The total number of samples stored for simple sampling types (like sum, count). For Prometheus this is equivalent to the number of samples scraped and ingested. |`SimpleSamplesStored` |Count |Maximum |StampColor |No|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->