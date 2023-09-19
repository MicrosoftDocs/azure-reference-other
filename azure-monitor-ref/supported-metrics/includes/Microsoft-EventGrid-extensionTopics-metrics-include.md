---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.EventGrid/extensionTopics, arm
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Publish Failed Events<p><p>Total events failed to publish to this topic |`PublishFailCount` |Count |Total |ErrorType, Error|PT1M |Yes|
|Published Events<p><p>Total events published to this topic |`PublishSuccessCount` |Count |Total |No Dimensions|PT1M |Yes|
|Publish Success Latency<p><p>Publish success latency in milliseconds |`PublishSuccessLatencyInMs` |Milliseconds |Total |No Dimensions|PT1M |Yes|
|Unmatched Events<p><p>Total events not matching any of the event subscriptions for this topic |`UnmatchedEventCount` |Count |Total |No Dimensions|PT1M |Yes|