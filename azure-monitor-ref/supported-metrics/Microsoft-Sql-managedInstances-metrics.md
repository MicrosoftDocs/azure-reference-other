---
title: Supported metrics - Microsoft.Sql/managedInstances
description: Reference for Microsoft.Sql/managedInstances metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Sql/managedInstances  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Sql/managedInstances resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Average CPU percentage<p><p>Average CPU percentage |`avg_cpu_percent` |Percent |Average |No Dimensions |Yes|
|IO bytes read<p><p>IO bytes read |`io_bytes_read` |Bytes |Average |No Dimensions |Yes|
|IO bytes written<p><p>IO bytes written |`io_bytes_written` |Bytes |Average |No Dimensions |Yes|
|IO requests count<p><p>IO requests count |`io_requests` |Count |Average |No Dimensions |Yes|
|Storage space reserved<p><p>Storage space reserved |`reserved_storage_mb` |Count |Average |No Dimensions |Yes|
|Storage space used<p><p>Storage space used |`storage_space_used_mb` |Count |Average |No Dimensions |Yes|
|Virtual core count<p><p>Virtual core count |`virtual_core_count` |Count |Average |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->