---
title: Azure Monitor tables for microsoft.securityinsights/dnsnormalized
description: Azure Monitor tables for resource type microsoft.securityinsights/dnsnormalized
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
   
ms.date: 03/05/2024


---

# Resource log tables for microsoft.securityinsights/dnsnormalized  


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [ASimDnsActivityLogs](/azure/azure-monitor/reference/tables/ASimDnsActivityLogs)<p>The ASim DNS activity schema represents DNS protocol activity, which may be logged either by a DNS server or by a device sending DNS requests to a DNS server. The DNS protocol activity includes DNS queries, DNS server updates, and DNS bulk data transfers. Since the schema represents protocol activity, it is governed by RFCs and officially assigned parameter lists. The DNS activity schema does not represent DNS server audit events. | security | SecurityInsights | No| [Yes](/azure/azure-monitor/reference/queries/asimdnsactivitylogs)|

