---
title: Supported metrics - Microsoft.MachineLearningServices/workspaces/onlineEndpoints
description: Reference for Microsoft.MachineLearningServices/workspaces/onlineEndpoints metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.MachineLearningServices/workspaces/onlineEndpoints  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.MachineLearningServices/workspaces/onlineEndpoints resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Connections Active<p><p>The total number of concurrent TCP connections active from clients. |`ConnectionsActive` |Count |Average |No Dimensions |No|
|Data Collection Errors Per Minute<p><p>The number of data collection events dropped per minute. |`DataCollectionErrorsPerMinute` |Count |Average |deployment, reason, type |No|
|Data Collection Events Per Minute<p><p>The number of data collection events processed per minute. |`DataCollectionEventsPerMinute` |Count |Average |deployment, type |No|
|Network Bytes<p><p>The bytes per second served for the endpoint. |`NetworkBytes` |BytesPerSecond |Average |No Dimensions |No|
|New Connections Per Second<p><p>The average number of new TCP connections per second established from clients. |`NewConnectionsPerSecond` |CountPerSecond |Average |No Dimensions |No|
|Request Latency<p><p>The average complete interval of time taken for a request to be responded in milliseconds |`RequestLatency` |Milliseconds |Average |deployment |Yes|
|Request Latency P50<p><p>The average P50 request latency aggregated by all request latency values collected over the selected time period |`RequestLatency_P50` |Milliseconds |Average |deployment |Yes|
|Request Latency P90<p><p>The average P90 request latency aggregated by all request latency values collected over the selected time period |`RequestLatency_P90` |Milliseconds |Average |deployment |Yes|
|Request Latency P95<p><p>The average P95 request latency aggregated by all request latency values collected over the selected time period |`RequestLatency_P95` |Milliseconds |Average |deployment |Yes|
|Request Latency P99<p><p>The average P99 request latency aggregated by all request latency values collected over the selected time period |`RequestLatency_P99` |Milliseconds |Average |deployment |Yes|
|Requests Per Minute<p><p>The number of requests sent to online endpoint within a minute |`RequestsPerMinute` |Count |Average |deployment, statusCode, statusCodeClass, modelStatusCode |No|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->