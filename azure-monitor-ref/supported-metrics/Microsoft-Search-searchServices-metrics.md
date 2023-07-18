---
title: Supported metrics - Microsoft.Search/searchServices
description: Reference for Microsoft.Search/searchServices metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Search/searchServices  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Search/searchServices resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Document processed count<p><p>Number of documents processed |`DocumentsProcessedCount` |Count |Total |DataSourceName, Failed, IndexerName, IndexName, SkillsetName |Yes|
|Search Latency<p><p>Average search latency for the search service |`SearchLatency` |Seconds |Average |No Dimensions |Yes|
|Search queries per second<p><p>Search queries per second for the search service |`SearchQueriesPerSecond` |CountPerSecond |Average |No Dimensions |Yes|
|Skill execution invocation count<p><p>Number of skill executions |`SkillExecutionCount` |Count |Total |DataSourceName, Failed, IndexerName, SkillName, SkillsetName, SkillType |Yes|
|Throttled search queries percentage<p><p>Percentage of search queries that were throttled for the search service |`ThrottledSearchQueriesPercentage` |Percent |Average |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->