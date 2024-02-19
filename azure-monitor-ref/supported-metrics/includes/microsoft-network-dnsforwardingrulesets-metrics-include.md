---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Network/dnsForwardingRulesets, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Forwarding Rule Count**<br><br>This metric indicates the number of forwarding rules present in each DNS forwarding ruleset. |`ForwardingRuleCount` |Count |Average, Minimum, Maximum, Count |\<none\>|PT1H, PT6H, PT12H, P1D |No|
|**Virtual Network Link Count**<br><br>This metric indicates the number of associated virtual network links to a DNS forwarding ruleset. |`VirtualNetworkLinkCount` |Count |Average, Minimum, Maximum, Count |\<none\>|PT1H, PT6H, PT12H, P1D |No|