---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.graph/tenants
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AuditLogs](/azure/azure-monitor/reference/tables/AuditLogs)<p>Audit log for Azure Active Directory. Includes system activity information about user and group management managed applications and directory activities. | resources, security | LogManagement | No| -|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [SigninLogs](/azure/azure-monitor/reference/tables/SigninLogs)<p> | resources, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/signinlogs)|

  
