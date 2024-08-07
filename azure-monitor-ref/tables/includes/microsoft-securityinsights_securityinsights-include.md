---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/22/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.securityinsights/securityinsights
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [DnsAuditEvents](/azure/azure-monitor/reference/tables/DnsAuditEvents)<p>DNS server audit events enable change tracking on the DNS server. An audit event is logged each time server, zone, or resource record settings are changed. This includes operational events such as zone transfers, and DNSSEC zone signing and unsigning.  This table captures audit events that are not from dynamic updates. | security | SecurityInsights | No| -|
| [SecurityAlert](/azure/azure-monitor/reference/tables/SecurityAlert)<p>Alerts that been generated by security products. | security | AzureSecurityOfThings, Security, SecurityCenter, SecurityCenterFree, SecurityInsights | No| -|
| [SecurityEvent](/azure/azure-monitor/reference/tables/SecurityEvent)<p>Security events collected from windows machines by Azure Security Center or Azure Sentinel. | security | Security, SecurityInsights | No| [Yes](/azure/azure-monitor/reference/queries/securityevent)|

  
