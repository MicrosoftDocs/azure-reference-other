---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: microsoft.insights/autoscalesettings, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Metric Threshold<p><p>The configured autoscale threshold when autoscale ran. |`MetricThreshold` |Count |Average |MetricTriggerRule|PT1M |Yes|
|Observed Capacity<p><p>The capacity reported to autoscale when it executed. |`ObservedCapacity` |Count |Average |No Dimensions|PT1M |Yes|
|Observed Metric Value<p><p>The value computed by autoscale when executed |`ObservedMetricValue` |Count |Average |MetricTriggerSource|PT1M |Yes|
|Scale Actions Initiated<p><p>The direction of the scale operation. |`ScaleActionsInitiated` |Count |Total |ScaleDirection|PT1M |Yes|