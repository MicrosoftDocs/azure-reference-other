---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Network/azureFirewalls, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Application rules hit count**<br><br>Number of times Application rules were hit |`ApplicationRuleHit` |Count |Total |`Status`, `Reason`, `Protocol`|PT1M |Yes|
|**Data processed**<br><br>Total amount of data processed by this firewall |`DataProcessed` |Bytes |Total |\<none\>|PT1M |Yes|
|**Firewall health state**<br><br>Indicates the overall health of this firewall |`FirewallHealth` |Percent |Average |`Status`, `Reason`|PT1M |Yes|
|**Latency Probe**<br><br>Estimate of the average latency of the Firewall as measured by latency probe |`FirewallLatencyPng` |Milliseconds |Average |\<none\>|PT1M |Yes|
|**Network rules hit count**<br><br>Number of times Network rules were hit |`NetworkRuleHit` |Count |Total |`Status`, `Reason`, `Protocol`|PT1M |Yes|
|**SNAT port utilization**<br><br>Percentage of outbound SNAT ports currently in use |`SNATPortUtilization` |Percent |Average, Maximum |`Protocol`|PT1M |Yes|
|**Throughput**<br><br>Throughput processed by this firewall |`Throughput` |BitsPerSecond |Average |\<none\>|PT1M |No|