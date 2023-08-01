---
title: Supported metrics - Microsoft.Storage/storageTasks
description: Reference for Microsoft.Storage/storageTasks metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 08/01/2023
---
# Supported metrics for Microsoft.Storage/storageTasks  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Storage/storageTasks resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Objects operated count<p><p>The number of objects operated in storage task |`ObjectsOperatedCount` |Count |Total |AccountName, TaskAssignmentId |Yes|
|Objects failed count<p><p>The number of objects failed in storage task |`ObjectsOperationFailedCount` |Count |Total |AccountName, TaskAssignmentId |Yes|
|Objects succeeded count<p><p>The number of objects succeeded in storage task |`ObjectsOperationSucceededCount` |Count |Total |AccountName, TaskAssignmentId |Yes|
|Objects targed count<p><p>The number of objects targeted in storage task |`ObjectsTargetedCount` |Count |Total |AccountName, TaskAssignmentId |Yes|
|Runs count<p><p>The number of runs in storage task |`StorageTasksRunCount` |Count |Total |AccountName, TaskAssignmentId |Yes|
|Runs failed count<p><p>The number of runs failed in storage task |`StorageTasksRunFailureCount` |Count |Total |AccountName, TaskAssignmentId |Yes|
|Runs succeeded count<p><p>The number of runs succeeded in storage task |`StorageTasksRunSuccessCount` |Count |Total |AccountName, TaskAssignmentId |Yes|
|Runs failed with at least one operation count<p><p>The number of runs failed with at least one opeartion count in storage task |`StorageTasksRunWithFailedOperationCount` |Count |Total |AccountName, TaskAssignmentId |Yes|


<!--Gen Date:  Tue Aug 01 2023 10:39:24 GMT+0300 (Israel Daylight Time)-->