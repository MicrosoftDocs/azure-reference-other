---
title: Supported log categories - Microsoft.Network/networkSecurityPerimeters
description: Reference for Microsoft.Network/networkSecurityPerimeters in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported logs for Microsoft.Network/networkSecurityPerimeters  
<!-- Data source : naam-->


  The following table lists the types of logs available for the Microsoft.Network/networkSecurityPerimeters resource type.

|Category|Category Display Name|Costs To Export|
|---|---|---|
|NspCrossPerimeterInboundAllowed |Cross perimeter inbound access allowed by perimeter link. |Yes |
|NspCrossPerimeterOutboundAllowed |Cross perimeter outbound access allowed by perimeter link. |Yes |
|NspIntraPerimeterInboundAllowed |Inbound access allowed within same perimeter. |Yes |
|NspIntraPerimeterOutboundAllowed |Outbound attempted to same perimeter. NOTE: To be deprecated in future. |Yes |
|NspOutboundAttempt |Outbound attempted to same or different perimeter. |Yes |
|NspPrivateInboundAllowed |Private endpoint traffic allowed. |Yes |
|NspPublicInboundPerimeterRulesAllowed |Public inbound access allowed by NSP access rules. |Yes |
|NspPublicInboundPerimeterRulesDenied |Public inbound access denied by NSP access rules. |Yes |
|NspPublicInboundResourceRulesAllowed |Public inbound access allowed by PaaS resource rules. |Yes |
|NspPublicInboundResourceRulesDenied |Public inbound access denied by PaaS resource rules. |Yes |
|NspPublicOutboundPerimeterRulesAllowed |Public outbound access allowed by NSP access rules. |Yes |
|NspPublicOutboundPerimeterRulesDenied |Public outbound access denied by NSP access rules. |Yes |
|NspPublicOutboundResourceRulesAllowed |Public outbound access allowed by PaaS resource rules. |Yes |
|NspPublicOutboundResourceRulesDenied |Public outbound access denied by PaaS resource rules |Yes |


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->