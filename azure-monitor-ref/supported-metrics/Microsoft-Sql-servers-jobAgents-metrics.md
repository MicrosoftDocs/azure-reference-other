---
title: Supported metrics - Microsoft.Sql/servers/jobAgents
description: Reference for Microsoft.Sql/servers/jobAgents metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Sql/servers/jobAgents  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Sql/servers/jobAgents resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Elastic Jobs Executions Failed<p><p>Number of job executions that failed while trying to execute on target |`elastic_jobs_failed` |Count |Total |No Dimensions |Yes|
|Elastic Jobs Executions Successful<p><p>Number of job executions that were able to successfully execute on target |`elastic_jobs_successful` |Count |Total |No Dimensions |Yes|
|Elastic Jobs Executions Timed Out<p><p>Number of job executions that expired before execution was able to finish on target. |`elastic_jobs_timeout` |Count |Total |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->