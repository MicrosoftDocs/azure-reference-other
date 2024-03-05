---
title: Azure Monitor tables for microsoft.securityinsights/asimtables
description: Azure Monitor tables for resource type microsoft.securityinsights/asimtables
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
   
ms.date: 03/05/2024


---

# Resource log tables for microsoft.securityinsights/asimtables  


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [ASimDhcpEventLogs](/azure/azure-monitor/reference/tables/ASimDhcpEventLogs)<p>The ASIM DHCP schema represents DHCP server activity, including serving requests for DHCP IP address leased from client systems and updating a DNS server with the leases granted. | security | SecurityInsights | No| -|
| [ASimFileEventLogs](/azure/azure-monitor/reference/tables/ASimFileEventLogs)<p>The Advanced Security Information Model (ASIM) File Event normalization schema describes file activity such as creating, modifying, or deleting files or documents. | security | SecurityInsights | No| -|
| [ASimRegistryEventLogs](/azure/azure-monitor/reference/tables/ASimRegistryEventLogs)<p>The ASim Registry Event schema represents Windows activity of creating, modifying, or deleting Windows Registry entities. Registry events are specific to Windows systems, but are reported by different systems that monitor Windows, such as EDR (End Point Detection and Response) systems, Sysmon, or Windows itself. | security | SecurityInsights | No| -|
| [ASimUserManagementActivityLogs](/azure/azure-monitor/reference/tables/ASimUserManagementActivityLogs)<p>The ASim User Management schema represents user management activities, such as creating a user or a group, changing user attribute, or adding a user to a group. Such events are reported, for example, by operating systems, directory services, identity management systems, and any other system reporting on its local user management activity. | security | SecurityInsights | No| -|

