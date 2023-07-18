---
title: Supported metrics - microsoft.purview/accounts
description: Reference for microsoft.purview/accounts metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for microsoft.purview/accounts  
<!-- Data source : naam-->


The following table lists the metrics available for the microsoft.purview/accounts resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Data Map Capacity Units<p><p>Indicates Data Map Capacity Units. |`DataMapCapacityUnits` |Count |Total |No Dimensions |Yes|
|Data Map Storage Size<p><p>Indicates the data map storage size. |`DataMapStorageSize` |Bytes |Total |No Dimensions |Yes|
|Scan Cancelled<p><p>Indicates the number of scans cancelled. |`ScanCancelled` |Count |Total |No Dimensions |Yes|
|Scan Completed<p><p>Indicates the number of scans completed successfully. |`ScanCompleted` |Count |Total |No Dimensions |Yes|
|Scan Failed<p><p>Indicates the number of scans failed. |`ScanFailed` |Count |Total |No Dimensions |Yes|
|Scan time taken<p><p>Indicates the total scan time in seconds. |`ScanTimeTaken` |Seconds |Total |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->