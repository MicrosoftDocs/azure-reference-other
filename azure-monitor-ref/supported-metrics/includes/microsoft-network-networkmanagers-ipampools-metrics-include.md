---
ms.service: azure-monitor
ms.topic: include
ms.date: 11/09/2023
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
|**Compliant resources percentage**<p><p>Ratio of compliant resources to total resources associated to the pool. |`CompliantResourcesPercentage` |Percent |Average |\<none\>|PT1M |Yes|
|**IPs allocated count**<p><p>Number of IPs in pool that have been allocated. |`IpsAllocatedCount` |Count |Average |\<none\>|PT1M |Yes|
|**IPs allocated percentage**<p><p>Percentage of IPs in pool that have been allocated. |`IpsAllocatedPercentage` |Percent |Average |\<none\>|PT1M |Yes|
|**IPs available count**<p><p>Number of IPs in the pool that are available. |`IpsAvailableCount` |Count |Average |\<none\>|PT1M |Yes|
|**IPs available percentage**<p><p>Number of IPs in the pool that are available. |`IpsAvailablePercentage` |Percent |Average |\<none\>|PT1M |Yes|
|**IPs used count**<p><p>Number of IPs in the pool that have been used. |`IpsUsedCount` |Count |Average |\<none\>|PT1M |Yes|
|**IPs used percentage**<p><p>Percentage of IPs in the pool that have been used. |`IpsUsedPercentage` |Percent |Average |\<none\>|PT1M |Yes|
|**Noncompliant resources count**<p><p>Number of noncompliant resources associated to the pool. |`NoncompliantResourcesCount` |Count |Average |\<none\>|PT1M |Yes|
|**Noncompliant resources percentage**<p><p>Ratio of noncompliant resources to total resources associated to the pool. |`NoncompliantResourcesPercentage` |Percent |Average |\<none\>|PT1M |Yes|