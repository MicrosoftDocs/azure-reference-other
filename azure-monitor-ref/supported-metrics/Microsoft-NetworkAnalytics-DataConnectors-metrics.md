---
title: Supported metrics - Microsoft.NetworkAnalytics/DataConnectors
description: Reference for Microsoft.NetworkAnalytics/DataConnectors metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.NetworkAnalytics/DataConnectors  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.NetworkAnalytics/DataConnectors resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Data Ingested<p><p>The volume of data ingested by the pipeline (bytes). |`DataIngested` |Bytes |Total |No Dimensions |No|
|Malformed Data<p><p>The number of files unable to be processed by the pipeline. |`MalformedData` |Count |Total |No Dimensions |Yes|
|Malformed Records<p><p>The number of records unable to be processed by the pipeline. |`MalformedRecords` |Count |Total |No Dimensions |No|
|Processed File Count<p><p>The number of files processed by the data connector. |`ProcessedFileCount` |Count |Total |No Dimensions |Yes|
|Running<p><p>Values greater than 0 indicate that the pipeline is ready to process data. |`Running` |Unspecified |Count |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->