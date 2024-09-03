---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/02/2024
ms.author: orens
author: osalzberg
ms.custom: Microsoft.Network/networkSecurityPerimeters, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`NspCrossPerimeterInboundAllowed` |Cross perimeter inbound access allowed by perimeter link. |[NSPAccessLogs](/azure/azure-monitor/reference/tables/nspaccesslogs)<p>Logs of Network Security Perimeter (NSP) inbound access allowed based on NSP access rules.|No|No||Yes |
|`NspCrossPerimeterOutboundAllowed` |Cross perimeter outbound access allowed by perimeter link. ||No|No||Yes |
|`NspIntraPerimeterInboundAllowed` |Inbound access allowed within same perimeter. |[NSPAccessLogs](/azure/azure-monitor/reference/tables/nspaccesslogs)<p>Logs of Network Security Perimeter (NSP) inbound access allowed based on NSP access rules.|No|No||Yes |
|`NspOutboundAttempt` |Outbound attempted to same or different perimeter. |[NSPAccessLogs](/azure/azure-monitor/reference/tables/nspaccesslogs)<p>Logs of Network Security Perimeter (NSP) inbound access allowed based on NSP access rules.|No|No||Yes |
|`NspPrivateInboundAllowed` |Private endpoint traffic allowed. |[NSPAccessLogs](/azure/azure-monitor/reference/tables/nspaccesslogs)<p>Logs of Network Security Perimeter (NSP) inbound access allowed based on NSP access rules.|No|No||Yes |
|`NspPublicInboundPerimeterRulesAllowed` |Public inbound access allowed by NSP access rules. |[NSPAccessLogs](/azure/azure-monitor/reference/tables/nspaccesslogs)<p>Logs of Network Security Perimeter (NSP) inbound access allowed based on NSP access rules.|No|No||Yes |
|`NspPublicInboundPerimeterRulesDenied` |Public inbound access denied by NSP access rules. |[NSPAccessLogs](/azure/azure-monitor/reference/tables/nspaccesslogs)<p>Logs of Network Security Perimeter (NSP) inbound access allowed based on NSP access rules.|No|No||Yes |
|`NspPublicInboundResourceRulesAllowed` |Public inbound access allowed by PaaS resource rules. |[NSPAccessLogs](/azure/azure-monitor/reference/tables/nspaccesslogs)<p>Logs of Network Security Perimeter (NSP) inbound access allowed based on NSP access rules.|No|No||Yes |
|`NspPublicInboundResourceRulesDenied` |Public inbound access denied by PaaS resource rules. |[NSPAccessLogs](/azure/azure-monitor/reference/tables/nspaccesslogs)<p>Logs of Network Security Perimeter (NSP) inbound access allowed based on NSP access rules.|No|No||Yes |
|`NspPublicOutboundPerimeterRulesAllowed` |Public outbound access allowed by NSP access rules. |[NSPAccessLogs](/azure/azure-monitor/reference/tables/nspaccesslogs)<p>Logs of Network Security Perimeter (NSP) inbound access allowed based on NSP access rules.|No|No||Yes |
|`NspPublicOutboundPerimeterRulesDenied` |Public outbound access denied by NSP access rules. |[NSPAccessLogs](/azure/azure-monitor/reference/tables/nspaccesslogs)<p>Logs of Network Security Perimeter (NSP) inbound access allowed based on NSP access rules.|No|No||Yes |
|`NspPublicOutboundResourceRulesAllowed` |Public outbound access allowed by PaaS resource rules. |[NSPAccessLogs](/azure/azure-monitor/reference/tables/nspaccesslogs)<p>Logs of Network Security Perimeter (NSP) inbound access allowed based on NSP access rules.|No|No||Yes |
|`NspPublicOutboundResourceRulesDenied` |Public outbound access denied by PaaS resource rules |[NSPAccessLogs](/azure/azure-monitor/reference/tables/nspaccesslogs)<p>Logs of Network Security Perimeter (NSP) inbound access allowed based on NSP access rules.|No|No||Yes |