---
title: Supported metrics - Microsoft.HealthcareApis/workspaces/fhirservices
description: Reference for Microsoft.HealthcareApis/workspaces/fhirservices metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.HealthcareApis/workspaces/fhirservices  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.HealthcareApis/workspaces/fhirservices resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Availability<p><p>The availability rate of the service. |`Availability` |Percent |Average |No Dimensions |Yes|
|Total Data Size<p><p>Total size of the data in the backing database, in bytes. |`TotalDataSize` |Bytes |Total |No Dimensions |Yes|
|Total Errors<p><p>The total number of internal server errors encountered by the service. |`TotalErrors` |Count |Sum |Protocol, StatusCode, StatusCodeClass, StatusCodeText |Yes|
|Total Latency<p><p>The response latency of the service. |`TotalLatency` |Milliseconds |Average |Protocol |Yes|
|Total Requests<p><p>The total number of requests received by the service. |`TotalRequests` |Count |Sum |Protocol |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->