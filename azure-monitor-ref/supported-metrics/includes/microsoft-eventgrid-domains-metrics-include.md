---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.EventGrid/domains, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Advanced Filter Evaluations**<p><p>Total advanced filters evaluated across event subscriptions for this topic. |`AdvancedFilterEvaluationCount` |Count |Total |`Topic`, `EventSubscriptionName`, `DomainEventSubscriptionName`|PT1M |Yes|
|**Dead Lettered Events**<p><p>Total dead lettered events matching to this event subscription |`DeadLetteredCount` |Count |Total |`Topic`, `EventSubscriptionName`, `DomainEventSubscriptionName`, `DeadLetterReason`|PT1M |Yes|
|**Delivery Failed Events**<p><p>Total events failed to deliver to this event subscription |`DeliveryAttemptFailCount` |Count |Total |`Topic`, `EventSubscriptionName`, `DomainEventSubscriptionName`, `Error`, `ErrorType`|PT1M |No|
|**Delivered Events**<p><p>Total events delivered to this event subscription |`DeliverySuccessCount` |Count |Total |`Topic`, `EventSubscriptionName`, `DomainEventSubscriptionName`|PT1M |Yes|
|**Destination Processing Duration**<p><p>Destination processing duration in milliseconds |`DestinationProcessingDurationInMs` |MilliSeconds |Average |`Topic`, `EventSubscriptionName`, `DomainEventSubscriptionName`|PT1M |No|
|**Dropped Events**<p><p>Total dropped events matching to this event subscription |`DroppedEventCount` |Count |Total |`Topic`, `EventSubscriptionName`, `DomainEventSubscriptionName`, `DropReason`|PT1M |Yes|
|**Matched Events**<p><p>Total events matched to this event subscription |`MatchedEventCount` |Count |Total |`Topic`, `EventSubscriptionName`, `DomainEventSubscriptionName`|PT1M |Yes|
|**Publish Failed Events**<p><p>Total events failed to publish to this topic |`PublishFailCount` |Count |Total |`Topic`, `ErrorType`, `Error`|PT1M |Yes|
|**Published Events**<p><p>Total events published to this topic |`PublishSuccessCount` |Count |Total |`Topic`|PT1M |Yes|
|**Publish Success Latency**<p><p>Publish success latency in milliseconds |`PublishSuccessLatencyInMs` |MilliSeconds |Total |\<none\>|PT1M |Yes|