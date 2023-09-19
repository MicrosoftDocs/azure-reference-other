---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.DataShare/accounts, arm
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Received Share Failed Snapshots<p><p>Number of received share failed snapshots in the account |`FailedShareSubscriptionSynchronizations` |Count |Count |No Dimensions|PT1D |Yes|
|Sent Share Failed Snapshots<p><p>Number of sent share failed snapshots in the account |`FailedShareSynchronizations` |Count |Count |No Dimensions|PT1D |Yes|
|Sent Shares<p><p>Number of sent shares in the account |`ShareCount` |Count |Maximum |ShareName|PT1D |Yes|
|Received Shares<p><p>Number of received shares in the account |`ShareSubscriptionCount` |Count |Maximum |ShareSubscriptionName|PT1D |Yes|
|Received Share Succeeded Snapshots<p><p>Number of received share succeeded snapshots in the account |`SucceededShareSubscriptionSynchronizations` |Count |Count |No Dimensions|PT1D |Yes|
|Sent Share Succeeded Snapshots<p><p>Number of sent share succeeded snapshots in the account |`SucceededShareSynchronizations` |Count |Count |No Dimensions|PT1D |Yes|