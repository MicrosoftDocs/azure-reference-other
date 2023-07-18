---
title: Supported metrics - Microsoft.BotService/listqnamakerendpointkeys
description: Reference for Microsoft.BotService/listqnamakerendpointkeys metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.BotService/listqnamakerendpointkeys  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.BotService/listqnamakerendpointkeys resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Requests Latencies<p><p>How long it takes to get request response |`RequestLatency` |Milliseconds |Average |Operation, Authentication, Protocol, ResourceId, Region |Yes|
|Requests Traffic<p><p>Number of requests within a given period of time |`RequestsTraffic` |Count |Average |Operation, Authentication, Protocol, ResourceId, Region, StatusCode, StatusCodeClass, StatusText |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->