---
title: Supported metrics - Microsoft.MixedReality/spatialAnchorsAccounts
description: Reference for Microsoft.MixedReality/spatialAnchorsAccounts metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.MixedReality/spatialAnchorsAccounts  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.MixedReality/spatialAnchorsAccounts resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Anchors Created<p><p>Number of Anchors created |`AnchorsCreated` |Count |Total |DeviceFamily, SDKVersion |Yes|
|Anchors Deleted<p><p>Number of Anchors deleted |`AnchorsDeleted` |Count |Total |DeviceFamily, SDKVersion |Yes|
|Anchors Queried<p><p>Number of Spatial Anchors queried |`AnchorsQueried` |Count |Total |DeviceFamily, SDKVersion |Yes|
|Anchors Updated<p><p>Number of Anchors updated |`AnchorsUpdated` |Count |Total |DeviceFamily, SDKVersion |Yes|
|Poses Found<p><p>Number of Poses returned |`PosesFound` |Count |Total |DeviceFamily, SDKVersion |Yes|
|Total Daily Anchors<p><p>Total number of Anchors - Daily |`TotalDailyAnchors` |Count |Average |DeviceFamily, SDKVersion |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->