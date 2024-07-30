---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.PlayFab/titles, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Traffic|**PlayerLoggedInCount**<br><br>Number of logins by any player in a given title |`PlayerLoggedInCount` |Count |Average, Maximum, Minimum, Total, Count |`TitleId`|PT1M |Yes|