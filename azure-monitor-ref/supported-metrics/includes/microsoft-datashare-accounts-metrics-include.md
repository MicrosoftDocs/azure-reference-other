---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.DataShare/accounts, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Received Share Failed Snapshots**<p><p>Number of received share failed snapshots in the account |`FailedShareSubscriptionSynchronizations` |Count |Count |\<none\>|PT1D |Yes|
|**Sent Share Failed Snapshots**<p><p>Number of sent share failed snapshots in the account |`FailedShareSynchronizations` |Count |Count |\<none\>|PT1D |Yes|
|**Sent Shares**<p><p>Number of sent shares in the account |`ShareCount` |Count |Maximum |`ShareName`|PT1D |Yes|
|**Received Shares**<p><p>Number of received shares in the account |`ShareSubscriptionCount` |Count |Maximum |`ShareSubscriptionName`|PT1D |Yes|
|**Received Share Succeeded Snapshots**<p><p>Number of received share succeeded snapshots in the account |`SucceededShareSubscriptionSynchronizations` |Count |Count |\<none\>|PT1D |Yes|
|**Sent Share Succeeded Snapshots**<p><p>Number of sent share succeeded snapshots in the account |`SucceededShareSynchronizations` |Count |Count |\<none\>|PT1D |Yes|