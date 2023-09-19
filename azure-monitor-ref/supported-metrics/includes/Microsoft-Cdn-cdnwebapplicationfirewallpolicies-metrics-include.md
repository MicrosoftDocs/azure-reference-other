---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Cdn/cdnwebapplicationfirewallpolicies, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Web Application Firewall Request Count<p><p>The number of client requests processed by the Web Application Firewall |`WebApplicationFirewallRequestCount` |Count |Total |PolicyName, RuleName, Action|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|