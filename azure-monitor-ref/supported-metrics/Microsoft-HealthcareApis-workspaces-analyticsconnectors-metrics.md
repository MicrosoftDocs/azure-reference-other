---
title: Supported metrics - Microsoft.HealthcareApis/workspaces/analyticsconnectors
description: Reference for Microsoft.HealthcareApis/workspaces/analyticsconnectors metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.HealthcareApis/workspaces/analyticsconnectors  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.HealthcareApis/workspaces/analyticsconnectors resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Analytics Connector Health Status<p><p>The health status of analytics connector |`AnalyticsConnectorHealthStatus` |Count |Sum |Operation, Component |Yes|
|Analytics Connector Process Latency<p><p>The response latency of the service. |`AnalyticsConnectorResourceLatency` |Milliseconds |Average |No Dimensions |Yes|
|Analytics Connector Successful Data Size<p><p>The size of data successfully processed by the analytics connector |`AnalyticsConnectorSuccessfulDataSize` |Count |Sum |No Dimensions |Yes|
|Analytics Connector Successful Resource Count<p><p>The amount of data successfully processed by the analytics connector |`AnalyticsConnectorSuccessfulResourceCount` |Count |Sum |No Dimensions |Yes|
|Analytics Connector Total Error Count<p><p>The total number of errors logged by the analytics connector |`AnalyticsConnectorTotalError` |Count |Sum |ErrorType, Operation |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->