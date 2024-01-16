---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.EventGrid/partnerNamespaces, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Publish Failed Events**<p><p>Total events failed to publish to this partner namespace |`PublishFailCount` |Count |Total |`ErrorType`, `Error`|PT1M |Yes|
|**Published Events**<p><p>Total events published to this partner namespace |`PublishSuccessCount` |Count |Total |\<none\>|PT1M |Yes|
|**Publish Success Latency**<p><p>Publish success latency in milliseconds |`PublishSuccessLatencyInMs` |MilliSeconds |Total |\<none\>|PT1M |Yes|
|**Unmatched Events**<p><p>Total events not matching any of the partner topics |`UnmatchedEventCount` |Count |Total |\<none\>|PT1M |Yes|