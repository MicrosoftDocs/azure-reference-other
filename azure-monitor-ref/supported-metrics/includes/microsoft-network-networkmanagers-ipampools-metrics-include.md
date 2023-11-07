---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Network/networkManagers/ipamPools, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Compliant resources count**<p><p>Number of compliant resources associated to the pool. |`CompliantResourcesCount` |Count |Average |\<none\>|PT1M |Yes|
|**Incompliant resources count**<p><p>Number of incompliant resources associated to the pool. |`IncompliantResourcesCount` |Count |Average |\<none\>|PT1M |Yes|
|**Incompliant resources percentage**<p><p>Ratio of incompliant resources to total resources associated to the pool. |`IncompliantResourcesPercentage` |Percent |Average |\<none\>|PT1M |Yes|
|**IPs used count**<p><p>Number of IPs in the pool that have been used. |`IpsUsedCount` |Count |Average |\<none\>|PT1M |Yes|
|**IPs used percentage**<p><p>Percentage of IPs in the pool that have been used. |`IpsUsedPercentage` |Percent |Average |\<none\>|PT1M |Yes|
|**Pool allocation percentage**<p><p>Percentage of CIDRs in pool that have been allocated. |`PoolAllocationPercentage` |Percent |Average |\<none\>|PT1M |Yes|