---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.EventGrid/eventSubscriptions, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Dead Lettered Events**<br><br>Total dead lettered events matching to this event subscription |`DeadLetteredCount` |Count |Total |`DeadLetterReason`|PT1M |Yes|
|**Delivery Failed Events**<br><br>Total events failed to deliver to this event subscription |`DeliveryAttemptFailCount` |Count |Total |`Error`, `ErrorType`|PT1M |No|
|**Delivered Events**<br><br>Total events delivered to this event subscription |`DeliverySuccessCount` |Count |Total |\<none\>|PT1M |Yes|
|**Destination Processing Duration**<br><br>Destination processing duration in milliseconds |`DestinationProcessingDurationInMs` |Milliseconds |Average |\<none\>|PT1M |No|
|**Dropped Events**<br><br>Total dropped events matching to this event subscription |`DroppedEventCount` |Count |Total |`DropReason`|PT1M |Yes|
|**Matched Events**<br><br>Total events matched to this event subscription |`MatchedEventCount` |Count |Total |\<none\>|PT1M |Yes|