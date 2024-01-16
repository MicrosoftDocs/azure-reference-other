---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.PowerBIDedicated/capacities, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**CPU (Gen2)**<p><p>CPU Utilization. Supported only for Power BI Embedded Generation 2 resources. |`cpu_metric` |Percent |Average |\<none\>|PT1M |Yes|
|**Overload (Gen2)**<p><p>Resource Overload, 1 if resource is overloaded, otherwise 0. Supported only for Power BI Embedded Generation 2 resources. |`overload_metric` |Count |Average |\<none\>|PT1M |Yes|