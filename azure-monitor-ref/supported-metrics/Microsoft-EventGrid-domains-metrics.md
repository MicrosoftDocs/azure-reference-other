---
title: Supported metrics - Microsoft.EventGrid/domains
description: Reference for Microsoft.EventGrid/domains metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.EventGrid/domains  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.EventGrid/domains resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Advanced Filter Evaluations<p><p>Total advanced filters evaluated across event subscriptions for this topic. |`AdvancedFilterEvaluationCount` |Count |Total |Topic, EventSubscriptionName, DomainEventSubscriptionName |Yes|
|Dead Lettered Events<p><p>Total dead lettered events matching to this event subscription |`DeadLetteredCount` |Count |Total |Topic, EventSubscriptionName, DomainEventSubscriptionName, DeadLetterReason |Yes|
|Delivery Failed Events<p><p>Total events failed to deliver to this event subscription |`DeliveryAttemptFailCount` |Count |Total |Topic, EventSubscriptionName, DomainEventSubscriptionName, Error, ErrorType |No|
|Delivered Events<p><p>Total events delivered to this event subscription |`DeliverySuccessCount` |Count |Total |Topic, EventSubscriptionName, DomainEventSubscriptionName |Yes|
|Destination Processing Duration<p><p>Destination processing duration in milliseconds |`DestinationProcessingDurationInMs` |MilliSeconds |Average |Topic, EventSubscriptionName, DomainEventSubscriptionName |No|
|Dropped Events<p><p>Total dropped events matching to this event subscription |`DroppedEventCount` |Count |Total |Topic, EventSubscriptionName, DomainEventSubscriptionName, DropReason |Yes|
|Matched Events<p><p>Total events matched to this event subscription |`MatchedEventCount` |Count |Total |Topic, EventSubscriptionName, DomainEventSubscriptionName |Yes|
|Publish Failed Events<p><p>Total events failed to publish to this topic |`PublishFailCount` |Count |Total |Topic, ErrorType, Error |Yes|
|Published Events<p><p>Total events published to this topic |`PublishSuccessCount` |Count |Total |Topic |Yes|
|Publish Success Latency<p><p>Publish success latency in milliseconds |`PublishSuccessLatencyInMs` |MilliSeconds |Total |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->