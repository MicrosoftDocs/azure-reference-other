---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: microsoft.network/bastionHosts, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Bastion Communication Status**<p><p>Communication status shows 1 if all communication is good and 0 if its bad. |`pingmesh` |Count |Average |\<none\>|PT1M |No|
|**Session Count**<p><p>Sessions Count for the Bastion. View in sum and per instance. |`sessions` |Count |Total, Average |`host`|PT5M, PT15M |No|
|**Total Memory**<p><p>Total memory stats. |`total` |Count |Average |`host`|PT1M |Yes|
|**CPU Usage**<p><p>CPU Usage stats. |`usage_user` |Count |Average |`cpu`, `host`|PT1M |No|
|**Memory Usage**<p><p>Memory Usage stats. |`used` |Count |Average |`host`|PT1M |Yes|