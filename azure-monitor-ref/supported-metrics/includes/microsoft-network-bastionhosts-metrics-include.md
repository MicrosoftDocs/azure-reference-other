---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: microsoft.network/bastionHosts, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Availability|**Bastion Communication Status**<p><p>Communication status shows 1 if all communication is good and 0 if its bad. |`pingmesh` |Count |Average |\<none\>|PT1M |No|
|Traffic|**Session Count**<p><p>Sessions Count for the Bastion. View in sum and per instance. |`sessions` |Count |Total, Average |`host`|PT5M, PT15M |No|
|Saturation|**Total Memory**<p><p>Total memory stats. |`total` |Count |Average |`host`|PT1M |Yes|
|Saturation|**CPU Usage**<p><p>CPU Usage stats. |`usage_user` |Count |Average |`cpu`, `host`|PT1M |No|
|Saturation|**Memory Usage**<p><p>Memory Usage stats. |`used` |Count |Average |`host`|PT1M |Yes|