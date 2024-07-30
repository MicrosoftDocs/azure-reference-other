---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: microsoft.hybridnetwork/virtualnetworkfunctions, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Availability|**Average CPU Utilization**<br><br>Total average percentage of virtual CPU utilization at one minute interval. The total number of virtual CPU is based on user configured value in SKU definition. Further filter can be applied based on RoleName defined in SKU. |`HyperVVirtualProcessorUtilization` |Percent |Average, Maximum, Minimum |`InstanceName`|PT1M |Yes|