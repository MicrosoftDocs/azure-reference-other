---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.PowerBIDedicated/capacities, arm
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|CPU (Gen2)<p><p>CPU Utilization. Supported only for Power BI Embedded Generation 2 resources. |`cpu_metric` |Percent |Average |No Dimensions|PT1M |Yes|
|Overload (Gen2)<p><p>Resource Overload, 1 if resource is overloaded, otherwise 0. Supported only for Power BI Embedded Generation 2 resources. |`overload_metric` |Count |Average |No Dimensions|PT1M |Yes|