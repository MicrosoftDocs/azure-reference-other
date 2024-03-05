---
title: Azure Monitor tables for microsoft.graph/tenants
description: Azure Monitor tables for resource type microsoft.graph/tenants
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
   
ms.date: 03/05/2024


---

# Resource log tables for microsoft.graph/tenants  


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AuditLogs](/azure/azure-monitor/reference/tables/AuditLogs)<p>Audit log for Azure Active Directory. Includes system activity information about user and group management managed applications and directory activities. | resources, security | LogManagement | No| -|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [SigninLogs](/azure/azure-monitor/reference/tables/SigninLogs)<p> | resources, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/signinlogs)|

