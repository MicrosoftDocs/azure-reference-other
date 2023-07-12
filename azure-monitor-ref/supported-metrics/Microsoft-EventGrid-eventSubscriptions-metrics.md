---
title: Supported metrics - Microsoft.EventGrid/eventSubscriptions
description: Reference for Microsoft.EventGrid/eventSubscriptions metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.EventGrid/eventSubscriptions  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.EventGrid/eventSubscriptions resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Dead Lettered Events<p><p>Total dead lettered events matching to this event subscription |`DeadLetteredCount` |Count |Total |DeadLetterReason |Yes|
|Delivery Failed Events<p><p>Total events failed to deliver to this event subscription |`DeliveryAttemptFailCount` |Count |Total |Error, ErrorType |No|
|Delivered Events<p><p>Total events delivered to this event subscription |`DeliverySuccessCount` |Count |Total |No Dimensions |Yes|
|Destination Processing Duration<p><p>Destination processing duration in milliseconds |`DestinationProcessingDurationInMs` |Milliseconds |Average |No Dimensions |No|
|Dropped Events<p><p>Total dropped events matching to this event subscription |`DroppedEventCount` |Count |Total |DropReason |Yes|
|Matched Events<p><p>Total events matched to this event subscription |`MatchedEventCount` |Count |Total |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->