---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.EventGrid/eventSubscriptions, arm
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Dead Lettered Events<p><p>Total dead lettered events matching to this event subscription |`DeadLetteredCount` |Count |Total |DeadLetterReason|PT1M |Yes|
|Delivery Failed Events<p><p>Total events failed to deliver to this event subscription |`DeliveryAttemptFailCount` |Count |Total |Error, ErrorType|PT1M |No|
|Delivered Events<p><p>Total events delivered to this event subscription |`DeliverySuccessCount` |Count |Total |No Dimensions|PT1M |Yes|
|Destination Processing Duration<p><p>Destination processing duration in milliseconds |`DestinationProcessingDurationInMs` |Milliseconds |Average |No Dimensions|PT1M |No|
|Dropped Events<p><p>Total dropped events matching to this event subscription |`DroppedEventCount` |Count |Total |DropReason|PT1M |Yes|
|Matched Events<p><p>Total events matched to this event subscription |`MatchedEventCount` |Count |Total |No Dimensions|PT1M |Yes|