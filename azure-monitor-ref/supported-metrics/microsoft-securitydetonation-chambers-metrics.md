---
title: Supported metrics - microsoft.securitydetonation/chambers
description: Reference for microsoft.securitydetonation/chambers metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for microsoft.securitydetonation/chambers  
<!-- Data source : naam-->


The following table lists the metrics available for the microsoft.securitydetonation/chambers resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Capacity Utilization<p><p>The percentage of the allocated capacity the resource is actively using. |`CapacityUtilization` |Percent |Maximum |Region |No|
|CPU Utilization<p><p>The percentage of the CPU that is being utilized across the resource. |`CpuUtilization` |Percent |Average |Region |No|
|CreateSubmission Api Results<p><p>The total number of CreateSubmission API requests, with return code. |`CreateSubmissionApiResult` |Count |Count |OperationName, ServiceTypeName, Region, HttpReturnCode |No|
|Available Disk Space<p><p>The percent amount of available disk space across the resource. |`PercentFreeDiskSpace` |Percent |Average |Region |No|
|Submission Duration<p><p>The submission duration (processing time), from creation to completion. |`SubmissionDuration` |MilliSeconds |Maximum |Region |No|
|Completed Submissions / Hr<p><p>The number of completed submissions / Hr. |`SubmissionsCompleted` |Count |Maximum |Region |No|
|Failed Submissions / Hr<p><p>The number of failed submissions / Hr. |`SubmissionsFailed` |Count |Maximum |Region |No|
|Outstanding Submissions<p><p>The average number of outstanding submissions that are queued for processing. |`SubmissionsOutstanding` |Count |Average |Region |No|
|Successful Submissions / Hr<p><p>The number of successful submissions / Hr. |`SubmissionsSucceeded` |Count |Maximum |Region |No|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->