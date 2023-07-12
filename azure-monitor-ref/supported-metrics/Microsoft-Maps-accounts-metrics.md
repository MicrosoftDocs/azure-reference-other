---
title: Supported metrics - Microsoft.Maps/accounts
description: Reference for Microsoft.Maps/accounts metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Maps/accounts  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.Maps/accounts resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Availability<p><p>Availability of the APIs |`Availability` |Percent |Average |ApiCategory, ApiName |Yes|
|Creator Usage<p><p>Azure Maps Creator usage statistics |`CreatorUsage` |Bytes |Average |ServiceName |No|
|Usage<p><p>Count of API calls |`Usage` |Count |Count |ApiCategory, ApiName, ResultType, ResponseCode |No|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->