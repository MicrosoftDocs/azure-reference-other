---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.PowerBIDedicated/capacities, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**CPU (Gen2)**<br><br>CPU Utilization. Supported only for Power BI Embedded Generation 2 resources. |`cpu_metric` |Percent |Average |\<none\>|PT1M |Yes|
|**Overload (Gen2)**<br><br>Resource Overload, 1 if resource is overloaded, otherwise 0. Supported only for Power BI Embedded Generation 2 resources. |`overload_metric` |Count |Average |\<none\>|PT1M |Yes|