---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.Network/dnsForwardingRulesets, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Forwarding Rule Count**<br><br>This metric indicates the number of forwarding rules present in each DNS forwarding ruleset. |`ForwardingRuleCount` |Count |Average, Minimum, Maximum, Count |\<none\>|PT1H, PT6H, PT12H, P1D |No|
|**Virtual Network Link Count**<br><br>This metric indicates the number of associated virtual network links to a DNS forwarding ruleset. |`VirtualNetworkLinkCount` |Count |Average, Minimum, Maximum, Count |\<none\>|PT1H, PT6H, PT12H, P1D |No|