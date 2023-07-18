---
title: Supported metrics - Microsoft.Synapse/workspaces/bigDataPools
description: Reference for Microsoft.Synapse/workspaces/bigDataPools metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Synapse/workspaces/bigDataPools  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Synapse/workspaces/bigDataPools resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|vCores allocated<p><p>Allocated vCores for an Apache Spark Pool |`BigDataPoolAllocatedCores` |Count |Maximum |SubmitterId |No|
|Memory allocated (GB)<p><p>Allocated Memory for Apach Spark Pool (GB) |`BigDataPoolAllocatedMemory` |Count |Maximum |SubmitterId |No|
|Active Apache Spark applications<p><p>Total Active Apache Spark Pool Applications |`BigDataPoolApplicationsActive` |Count |Maximum |JobState |No|
|Ended Apache Spark applications<p><p>Count of Apache Spark pool applications ended |`BigDataPoolApplicationsEnded` |Count |Total |JobType, JobResult |No|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->