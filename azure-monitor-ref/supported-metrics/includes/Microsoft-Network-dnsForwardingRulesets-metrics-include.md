---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Network/dnsForwardingRulesets, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Forwarding Rule Count<p><p>This metric indicates the number of forwarding rules present in each DNS forwarding ruleset. |`ForwardingRuleCount` |Count |Average, Minimum, Maximum, Count |No Dimensions|PT1H, PT6H, PT12H, P1D |No|
|Virtual Network Link Count<p><p>This metric indicates the number of associated virtual network links to a DNS forwarding ruleset. |`VirtualNetworkLinkCount` |Count |Average, Minimum, Maximum, Count |No Dimensions|PT1H, PT6H, PT12H, P1D |No|