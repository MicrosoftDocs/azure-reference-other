---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.EventGrid/extensionTopics, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Publish Failed Events**<br><br>Total events failed to publish to this topic |`PublishFailCount` |Count |Total |`ErrorType`, `Error`|PT1M |Yes|
|**Published Events**<br><br>Total events published to this topic |`PublishSuccessCount` |Count |Total |\<none\>|PT1M |Yes|
|**Publish Success Latency**<br><br>Publish success latency in milliseconds |`PublishSuccessLatencyInMs` |Milliseconds |Total |\<none\>|PT1M |Yes|
|**Unmatched Events**<br><br>Total events not matching any of the event subscriptions for this topic |`UnmatchedEventCount` |Count |Total |\<none\>|PT1M |Yes|