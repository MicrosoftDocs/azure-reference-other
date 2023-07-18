---
title: Supported metrics - Microsoft.EventGrid/partnerNamespaces
description: Reference for Microsoft.EventGrid/partnerNamespaces metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.EventGrid/partnerNamespaces  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.EventGrid/partnerNamespaces resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Publish Failed Events<p><p>Total events failed to publish to this partner namespace |`PublishFailCount` |Count |Total |ErrorType, Error |Yes|
|Published Events<p><p>Total events published to this partner namespace |`PublishSuccessCount` |Count |Total |No Dimensions |Yes|
|Publish Success Latency<p><p>Publish success latency in milliseconds |`PublishSuccessLatencyInMs` |MilliSeconds |Total |No Dimensions |Yes|
|Unmatched Events<p><p>Total events not matching any of the partner topics |`UnmatchedEventCount` |Count |Total |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->