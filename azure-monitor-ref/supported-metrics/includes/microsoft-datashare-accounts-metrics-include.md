---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.DataShare/accounts, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Received Share Failed Snapshots**<br><br>Number of received share failed snapshots in the account |`FailedShareSubscriptionSynchronizations` |Count |Count |\<none\>|P1D |Yes|
|**Sent Share Failed Snapshots**<br><br>Number of sent share failed snapshots in the account |`FailedShareSynchronizations` |Count |Count |\<none\>|P1D |Yes|
|**Sent Shares**<br><br>Number of sent shares in the account |`ShareCount` |Count |Maximum |`ShareName`|P1D |Yes|
|**Received Shares**<br><br>Number of received shares in the account |`ShareSubscriptionCount` |Count |Maximum |`ShareSubscriptionName`|P1D |Yes|
|**Received Share Succeeded Snapshots**<br><br>Number of received share succeeded snapshots in the account |`SucceededShareSubscriptionSynchronizations` |Count |Count |\<none\>|P1D |Yes|
|**Sent Share Succeeded Snapshots**<br><br>Number of sent share succeeded snapshots in the account |`SucceededShareSynchronizations` |Count |Count |\<none\>|P1D |Yes|