---
title: Supported metrics - Microsoft.Web/hostingenvironments/workerpools
description: Reference for Microsoft.Web/hostingenvironments/workerpools metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Web/hostingenvironments/workerpools  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Web/hostingenvironments/workerpools resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|CPU Percentage<p><p>The average CPU used across all instances of the worker pool. |`CpuPercentage` |Percent |Average |Instance |Yes|
|Memory Percentage<p><p>The average memory used across all instances of the worker pool. |`MemoryPercentage` |Percent |Average |Instance |Yes|
|Available Workers<p><p>Available Workers |`WorkersAvailable` |Count |Average |No Dimensions |Yes|
|Total Workers<p><p>Total Workers |`WorkersTotal` |Count |Average |No Dimensions |Yes|
|Used Workers<p><p>Used Workers |`WorkersUsed` |Count |Average |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->