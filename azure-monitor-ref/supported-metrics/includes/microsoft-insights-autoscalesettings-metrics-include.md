---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: microsoft.insights/autoscalesettings, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Metric Threshold**<br><br>The configured autoscale threshold when autoscale ran. |`MetricThreshold` |Count |Average |`MetricTriggerRule`|PT1M |Yes|
|**Observed Capacity**<br><br>The capacity reported to autoscale when it executed. |`ObservedCapacity` |Count |Average |\<none\>|PT1M |Yes|
|**Observed Metric Value**<br><br>The value computed by autoscale when executed |`ObservedMetricValue` |Count |Average |`MetricTriggerSource`|PT1M |Yes|
|**Scale Actions Initiated**<br><br>The direction of the scale operation. |`ScaleActionsInitiated` |Count |Total |`ScaleDirection`|PT1M |Yes|