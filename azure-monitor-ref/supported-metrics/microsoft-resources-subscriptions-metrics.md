---
title: Supported metrics - microsoft.resources/subscriptions
description: Reference for microsoft.resources/subscriptions metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for microsoft.resources/subscriptions  
<!-- Data source : naam-->


The following table lists the metrics available for the microsoft.resources/subscriptions resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Latency<p><p>Latency data for all requests to Azure Resource Manager |`Latency` |Seconds |Average |IsCustomerOriginated, Method, Namespace, RequestRegion, ResourceType, StatusCode, StatusCodeClass, Microsoft.SubscriptionId |No|
|Traffic<p><p>Traffic data for all requests to Azure Resource Manager |`Traffic` |Count |Count |IsCustomerOriginated, Method, Namespace, RequestRegion, ResourceType, StatusCode, StatusCodeClass, Microsoft.SubscriptionId |No|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->