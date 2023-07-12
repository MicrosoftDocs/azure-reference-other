---
title: Supported metrics - Microsoft.CustomProviders/resourceproviders
description: Reference for Microsoft.CustomProviders/resourceproviders metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.CustomProviders/resourceproviders  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.CustomProviders/resourceproviders resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Failed Requests<p><p>Gets the available logs for Custom Resource Providers |`FailedRequests` |Count |Total |HttpMethod, CallPath, StatusCode |Yes|
|Successful Requests<p><p>Successful requests made by the custom provider |`SuccessfullRequests` |Count |Total |HttpMethod, CallPath, StatusCode |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->