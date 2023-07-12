---
title: Supported metrics - microsoft.insights/autoscalesettings
description: Reference for microsoft.insights/autoscalesettings metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for microsoft.insights/autoscalesettings  
<!-- Data source : naam-->


The following table lists the metrics available for the microsoft.insights/autoscalesettings resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Metric Threshold<p><p>The configured autoscale threshold when autoscale ran. |`MetricThreshold` |Count |Average |MetricTriggerRule |Yes|
|Observed Capacity<p><p>The capacity reported to autoscale when it executed. |`ObservedCapacity` |Count |Average |No Dimensions |Yes|
|Observed Metric Value<p><p>The value computed by autoscale when executed |`ObservedMetricValue` |Count |Average |MetricTriggerSource |Yes|
|Scale Actions Initiated<p><p>The direction of the scale operation. |`ScaleActionsInitiated` |Count |Total |ScaleDirection |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->