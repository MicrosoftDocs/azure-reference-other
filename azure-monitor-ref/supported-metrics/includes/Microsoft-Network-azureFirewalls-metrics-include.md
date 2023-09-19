---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Network/azureFirewalls, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Application rules hit count<p><p>Number of times Application rules were hit |`ApplicationRuleHit` |Count |Total |Status, Reason, Protocol|PT1M |Yes|
|Data processed<p><p>Total amount of data processed by this firewall |`DataProcessed` |Bytes |Total |No Dimensions|PT1M |Yes|
|Firewall health state<p><p>Indicates the overall health of this firewall |`FirewallHealth` |Percent |Average |Status, Reason|PT1M |Yes|
|Latency Probe<p><p>Estimate of the average latency of the Firewall as measured by latency probe |`FirewallLatencyPng` |Milliseconds |Average |No Dimensions|PT1M |Yes|
|Network rules hit count<p><p>Number of times Network rules were hit |`NetworkRuleHit` |Count |Total |Status, Reason, Protocol|PT1M |Yes|
|SNAT port utilization<p><p>Percentage of outbound SNAT ports currently in use |`SNATPortUtilization` |Percent |Average, Maximum |Protocol|PT1M |Yes|
|Throughput<p><p>Throughput processed by this firewall |`Throughput` |BitsPerSecond |Average |No Dimensions|PT1M |No|