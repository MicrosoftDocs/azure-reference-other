---
title: Supported metrics - Wandisco.Fusion/migrators/dataTransferAgents
description: Reference for Wandisco.Fusion/migrators/dataTransferAgents metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Wandisco.Fusion/migrators/dataTransferAgents  
<!-- Data source : naam-->


The following table lists the metrics available for the Wandisco.Fusion/migrators/dataTransferAgents resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Bytes per Second.<p><p>Throughput speed of Bytes/second being utilised for a DTA. |`BytesPerSecond` |BytesPerSecond |Average |No Dimensions |Yes|
|DTA CPU Load<p><p>CPU consumption by the DTA process. |`DtaCPULoad` |Percent |Average |No Dimensions |Yes|
|Files Migration Count<p><p>This provides a running total of how many files have been migrated. |`FileMigrationCount` |Count |Total |No Dimensions |Yes|
|Migrated Data in Bytes<p><p>This provides a view of the successfully migrated Bytes for a given DTA |`MigratedDataInBytes` |Bytes |Total |No Dimensions |Yes|
|Number of Failed Paths<p><p>A count of which paths have failed to migrate. |`NumberOfFailedPaths` |Count |Total |No Dimensions |Yes|
|System CPU Load<p><p>Total CPU consumption. |`SystemCPULoad` |Percent |Average |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->