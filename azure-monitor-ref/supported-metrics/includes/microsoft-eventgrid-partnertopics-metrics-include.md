---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.EventGrid/partnerTopics, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Advanced Filter Evaluations**<br><br>Total advanced filters evaluated across event subscriptions for this partner topic. |`AdvancedFilterEvaluationCount` |Count |Total |`EventSubscriptionName`|PT1M |Yes|
|**Dead Lettered Events**<br><br>Total dead lettered events matching to this event subscription |`DeadLetteredCount` |Count |Total |`DeadLetterReason`, `EventSubscriptionName`|PT1M |Yes|
|**Delivery Failed Events**<br><br>Total events failed to deliver to this event subscription |`DeliveryAttemptFailCount` |Count |Total |`Error`, `ErrorType`, `EventSubscriptionName`|PT1M |No|
|**Delivered Events**<br><br>Total events delivered to this event subscription |`DeliverySuccessCount` |Count |Total |`EventSubscriptionName`|PT1M |Yes|
|**Destination Processing Duration**<br><br>Destination processing duration in milliseconds |`DestinationProcessingDurationInMs` |MilliSeconds |Average |`EventSubscriptionName`|PT1M |No|
|**Dropped Events**<br><br>Total dropped events matching to this event subscription |`DroppedEventCount` |Count |Total |`DropReason`, `EventSubscriptionName`|PT1M |Yes|
|**Matched Events**<br><br>Total events matched to this event subscription |`MatchedEventCount` |Count |Total |`EventSubscriptionName`|PT1M |Yes|
|**Published Events**<br><br>Total events published to this partner topic |`PublishSuccessCount` |Count |Total |\<none\>|PT1M |Yes|
|**Unmatched Events**<br><br>Total events not matching any of the event subscriptions for this partner topic |`UnmatchedEventCount` |Count |Total |\<none\>|PT1M |Yes|