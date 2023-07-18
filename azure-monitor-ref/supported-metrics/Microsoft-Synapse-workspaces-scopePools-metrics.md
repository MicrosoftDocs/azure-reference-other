---
title: Supported metrics - Microsoft.Synapse/workspaces/scopePools
description: Reference for Microsoft.Synapse/workspaces/scopePools metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Synapse/workspaces/scopePools  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Synapse/workspaces/scopePools resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|PN duration of SCOPE job<p><p>PN (process node) duration (Milliseconds) used by each SCOPE job |`ScopePoolJobPNMetric` |Milliseconds |Average |JobType, JobResult |Yes|
|Queued duration of SCOPE job<p><p>Queued duration (Milliseconds) used by each SCOPE job |`ScopePoolJobQueuedDurationMetric` |Milliseconds |Average |JobType |Yes|
|Running duration of SCOPE job<p><p>Running duration (Milliseconds) used by each SCOPE job |`ScopePoolJobRunningDurationMetric` |Milliseconds |Average |JobType, JobResult |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->