---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Web/hostingenvironments/workerpools, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|CPU Percentage<p><p>The average CPU used across all instances of the worker pool. |`CpuPercentage` |Percent |Average |Instance|PT1M |Yes|
|Memory Percentage<p><p>The average memory used across all instances of the worker pool. |`MemoryPercentage` |Percent |Average |Instance|PT1M |Yes|
|Available Workers<p><p>Available Workers |`WorkersAvailable` |Count |Average |No Dimensions|PT1M |Yes|
|Total Workers<p><p>Total Workers |`WorkersTotal` |Count |Average |No Dimensions|PT1M |Yes|
|Used Workers<p><p>Used Workers |`WorkersUsed` |Count |Average |No Dimensions|PT1M |Yes|