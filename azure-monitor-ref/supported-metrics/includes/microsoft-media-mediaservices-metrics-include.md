---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Media/mediaservices, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Asset count**<p><p>How many assets are already created in current media service account |`AssetCount` |Count |Average |\<none\>|PT1H, PT6H, PT12H, P1D |Yes|
|**Asset quota**<p><p>How many assets are allowed for current media service account |`AssetQuota` |Count |Average |\<none\>|PT1H, PT6H, PT12H, P1D |Yes|
|**Asset quota used percentage**<p><p>Asset used percentage in current media service account |`AssetQuotaUsedPercentage` |Percent |Average |\<none\>|PT1H, PT6H, PT12H, P1D |Yes|
|**Live event count**<p><p>The total number of live events in the current media services account |`ChannelsAndLiveEventsCount` |Count |Average |\<none\>|PT1M |Yes|
|**Content Key Policy count**<p><p>How many content key policies are already created in current media service account |`ContentKeyPolicyCount` |Count |Average |\<none\>|PT1H, PT6H, PT12H, P1D |Yes|
|**Content Key Policy quota**<p><p>How many content key polices are allowed for current media service account |`ContentKeyPolicyQuota` |Count |Average |\<none\>|PT1H, PT6H, PT12H, P1D |Yes|
|**Content Key Policy quota used percentage**<p><p>Content Key Policy used percentage in current media service account |`ContentKeyPolicyQuotaUsedPercentage` |Percent |Average |\<none\>|PT1H, PT6H, PT12H, P1D |Yes|
|**Job quota**<p><p>The Job quota for the current media service account. |`JobQuota` |Count |Average |\<none\>|PT1H, PT6H, PT12H, P1D |Yes|
|**Jobs Scheduled**<p><p>The number of Jobs in the Scheduled state. Counts on this metric only reflect jobs submitted through the v3 API. Jobs submitted through the v2 (Legacy) API are not counted. |`JobsScheduled` |Count |Average, Maximum, Minimum |\<none\>|PT1M |Yes|
|**Key request time**<p><p>The key delivery request status and latency in milliseconds for the current Media Service account. |`KeyDeliveryRequests` |Count |Average, Count |`KeyType`, `HttpStatusCode`|PT1H, PT6H, PT12H, P1D |No|
|**Max live event quota**<p><p>The maximum number of live events allowed in the current media services account |`MaxChannelsAndLiveEventsCount` |Count |Average |\<none\>|PT1M |Yes|
|**Max running live event quota**<p><p>The maximum number of running live events allowed in the current media services account |`MaxRunningChannelsAndLiveEventsCount` |Count |Average |\<none\>|PT1M |Yes|
|**Running live event count**<p><p>The total number of running live events in the current media services account |`RunningChannelsAndLiveEventsCount` |Count |Average |\<none\>|PT1M |Yes|
|**Streaming Policy count**<p><p>How many streaming policies are already created in current media service account |`StreamingPolicyCount` |Count |Average |\<none\>|PT1H, PT6H, PT12H, P1D |Yes|
|**Streaming Policy quota**<p><p>How many streaming policies are allowed for current media service account |`StreamingPolicyQuota` |Count |Average |\<none\>|PT1H, PT6H, PT12H, P1D |Yes|
|**Streaming Policy quota used percentage**<p><p>Streaming Policy used percentage in current media service account |`StreamingPolicyQuotaUsedPercentage` |Percent |Average |\<none\>|PT1H, PT6H, PT12H, P1D |Yes|
|**Transform quota**<p><p>The Transform quota for the current media service account. |`TransformQuota` |Count |Average |\<none\>|PT1H, PT6H, PT12H, P1D |Yes|