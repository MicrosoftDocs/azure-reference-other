---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.ContainerRegistry/registries, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**AgentPool CPU Time**<p><p>AgentPool CPU Time in seconds |`AgentPoolCPUTime` |Seconds |Total |\<none\>|PT1M |Yes|
|**Run Duration**<p><p>Run Duration in milliseconds |`RunDuration` |MilliSeconds |Total |\<none\>|PT1M |Yes|
|**Storage used**<p><p>The amount of storage used by the container registry. For a registry account, it's the sum of capacity used by all the repositories within a registry. It's sum of capacity used by shared layers, manifest files, and replica copies in each of its repositories. |`StorageUsed` |Bytes |Average |`Geolocation`|PT1H |Yes|
|**Successful Pull Count**<p><p>Number of successful image pulls |`SuccessfulPullCount` |Count |Total |\<none\>|PT1M |Yes|
|**Successful Push Count**<p><p>Number of successful image pushes |`SuccessfulPushCount` |Count |Total |\<none\>|PT1M |Yes|
|**Total Pull Count**<p><p>Number of image pulls in total |`TotalPullCount` |Count |Total |\<none\>|PT1M |Yes|
|**Total Push Count**<p><p>Number of image pushes in total |`TotalPushCount` |Count |Total |\<none\>|PT1M |Yes|