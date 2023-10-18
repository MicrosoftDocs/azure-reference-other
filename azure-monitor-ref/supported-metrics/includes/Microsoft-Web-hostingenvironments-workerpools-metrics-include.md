---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Web/hostingenvironments/workerpools, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**CPU Percentage**<p><p>The average CPU used across all instances of the worker pool. |`CpuPercentage` |Percent |Average |`Instance`|PT1M |Yes|
|**Memory Percentage**<p><p>The average memory used across all instances of the worker pool. |`MemoryPercentage` |Percent |Average |`Instance`|PT1M |Yes|
|**Available Workers**<p><p>Available Workers |`WorkersAvailable` |Count |Average |\<none\>|PT1M |Yes|
|**Total Workers**<p><p>Total Workers |`WorkersTotal` |Count |Average |\<none\>|PT1M |Yes|
|**Used Workers**<p><p>Used Workers |`WorkersUsed` |Count |Average |\<none\>|PT1M |Yes|