---
title: Supported metrics - Microsoft.DataLakeStore/accounts
description: Reference for Microsoft.DataLakeStore/accounts metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.DataLakeStore/accounts  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.DataLakeStore/accounts resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Data Read<p><p>Total amount of data read from the account. |`DataRead` |Bytes |Total |No Dimensions |Yes|
|Data Written<p><p>Total amount of data written to the account. |`DataWritten` |Bytes |Total |No Dimensions |Yes|
|Read Requests<p><p>Count of data read requests to the account. |`ReadRequests` |Count |Total |No Dimensions |Yes|
|Total Storage<p><p>Total amount of data stored in the account. |`TotalStorage` |Bytes |Maximum |No Dimensions |Yes|
|Write Requests<p><p>Count of data write requests to the account. |`WriteRequests` |Count |Total |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->