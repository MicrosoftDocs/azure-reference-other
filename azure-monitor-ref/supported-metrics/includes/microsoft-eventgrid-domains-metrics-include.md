---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.EventGrid/domains, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Advanced Filter Evaluations**<br><br>Total advanced filters evaluated across event subscriptions for this topic. |`AdvancedFilterEvaluationCount` |Count |Total |`Topic`, `EventSubscriptionName`, `DomainEventSubscriptionName`|PT1M |Yes|
|**Dead Lettered Events**<br><br>Total dead lettered events matching to this event subscription |`DeadLetteredCount` |Count |Total |`Topic`, `EventSubscriptionName`, `DomainEventSubscriptionName`, `DeadLetterReason`|PT1M |Yes|
|**Delivery Failed Events**<br><br>Total events failed to deliver to this event subscription |`DeliveryAttemptFailCount` |Count |Total |`Topic`, `EventSubscriptionName`, `DomainEventSubscriptionName`, `Error`, `ErrorType`|PT1M |No|
|**Delivered Events**<br><br>Total events delivered to this event subscription |`DeliverySuccessCount` |Count |Total |`Topic`, `EventSubscriptionName`, `DomainEventSubscriptionName`|PT1M |Yes|
|**Destination Processing Duration**<br><br>Destination processing duration in milliseconds |`DestinationProcessingDurationInMs` |MilliSeconds |Average |`Topic`, `EventSubscriptionName`, `DomainEventSubscriptionName`|PT1M |No|
|**Dropped Events**<br><br>Total dropped events matching to this event subscription |`DroppedEventCount` |Count |Total |`Topic`, `EventSubscriptionName`, `DomainEventSubscriptionName`, `DropReason`|PT1M |Yes|
|**Matched Events**<br><br>Total events matched to this event subscription |`MatchedEventCount` |Count |Total |`Topic`, `EventSubscriptionName`, `DomainEventSubscriptionName`|PT1M |Yes|
|**Publish Failed Events**<br><br>Total events failed to publish to this topic |`PublishFailCount` |Count |Total |`Topic`, `ErrorType`, `Error`|PT1M |Yes|
|**Published Events**<br><br>Total events published to this topic |`PublishSuccessCount` |Count |Total |`Topic`|PT1M |Yes|
|**Publish Success Latency**<br><br>Publish success latency in milliseconds |`PublishSuccessLatencyInMs` |MilliSeconds |Total |\<none\>|PT1M |Yes|