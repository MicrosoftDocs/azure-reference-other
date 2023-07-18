---
title: Supported metrics - Microsoft.DataLakeAnalytics/accounts
description: Reference for Microsoft.DataLakeAnalytics/accounts metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.DataLakeAnalytics/accounts  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.DataLakeAnalytics/accounts resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Cancelled AU Time<p><p>Total AU time for cancelled jobs. |`JobAUEndedCancelled` |Seconds |Total |No Dimensions |Yes|
|Failed AU Time<p><p>Total AU time for failed jobs. |`JobAUEndedFailure` |Seconds |Total |No Dimensions |Yes|
|Successful AU Time<p><p>Total AU time for successful jobs. |`JobAUEndedSuccess` |Seconds |Total |No Dimensions |Yes|
|Cancelled Jobs<p><p>Count of cancelled jobs. |`JobEndedCancelled` |Count |Total |No Dimensions |Yes|
|Failed Jobs<p><p>Count of failed jobs. |`JobEndedFailure` |Count |Total |No Dimensions |Yes|
|Successful Jobs<p><p>Count of successful jobs. |`JobEndedSuccess` |Count |Total |No Dimensions |Yes|
|Jobs in Stage<p><p>Number of jobs in each stage. |`JobStage` |Count |Total |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->