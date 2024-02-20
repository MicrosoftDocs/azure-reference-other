---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Web/hostingenvironments/workerpools, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**CPU Percentage**<br><br>The average CPU used across all instances of the worker pool. |`CpuPercentage` |Percent |Average |`Instance`|PT1M |Yes|
|**Memory Percentage**<br><br>The average memory used across all instances of the worker pool. |`MemoryPercentage` |Percent |Average |`Instance`|PT1M |Yes|
|**Available Workers**<br><br>Available Workers |`WorkersAvailable` |Count |Average |\<none\>|PT1M |Yes|
|**Total Workers**<br><br>Total Workers |`WorkersTotal` |Count |Average |\<none\>|PT1M |Yes|
|**Used Workers**<br><br>Used Workers |`WorkersUsed` |Count |Average |\<none\>|PT1M |Yes|