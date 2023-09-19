---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.DBforPostgreSQL/serversv2, arm
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Active Connections<p><p>Active Connections |`active_connections` |Count |Average, Maximum, Minimum |No Dimensions|PT1M |Yes|
|CPU percent<p><p>CPU percent |`cpu_percent` |Percent |Average, Maximum, Minimum |No Dimensions|PT1M |Yes|
|IOPS<p><p>IO Operations per second |`iops` |Count |Average, Maximum, Minimum |No Dimensions|PT1M |Yes|
|Memory percent<p><p>Memory percent |`memory_percent` |Percent |Average, Maximum, Minimum |No Dimensions|PT1M |Yes|
|Network Out<p><p>Network Out across active connections |`network_bytes_egress` |Bytes |Total |No Dimensions|PT1M |Yes|
|Network In<p><p>Network In across active connections |`network_bytes_ingress` |Bytes |Total |No Dimensions|PT1M |Yes|
|Storage percent<p><p>Storage percent |`storage_percent` |Percent |Average, Maximum, Minimum |No Dimensions|PT1M |Yes|
|Storage used<p><p>Storage used |`storage_used` |Bytes |Average, Maximum, Minimum |No Dimensions|PT1M |Yes|