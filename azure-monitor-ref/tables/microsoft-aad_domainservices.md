---
title: Azure Monitor tables for microsoft.aad/domainservices
description: Azure Monitor tables for resource type microsoft.aad/domainservices
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
   
ms.date: 03/05/2024


---

# Resource log tables for microsoft.aad/domainservices  


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AADDomainServicesAccountLogon](/azure/azure-monitor/reference/tables/AADDomainServicesAccountLogon)<p> | resources, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/aaddomainservicesaccountlogon)|
| [AADDomainServicesAccountManagement](/azure/azure-monitor/reference/tables/AADDomainServicesAccountManagement)<p> | resources, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/aaddomainservicesaccountmanagement)|
| [AADDomainServicesDNSAuditsDynamicUpdates](/azure/azure-monitor/reference/tables/AADDomainServicesDNSAuditsDynamicUpdates)<p>DNS server audit events enable change tracking on the DNS server. This table contains operational audit events for dynamic updates. |  | LogManagement | Yes| -|
| [AADDomainServicesDNSAuditsGeneral](/azure/azure-monitor/reference/tables/AADDomainServicesDNSAuditsGeneral)<p>DNS server audit events enable change tracking on the DNS server. An audit event is logged each time server, zone, or resource record settings are changed. This includes operational events such as zone transfers, and DNSSEC zone signing and unsigning.  This table captures audit events that are not from dynamic updates. |  | LogManagement | Yes| -|
| [AADDomainServicesDirectoryServiceAccess](/azure/azure-monitor/reference/tables/AADDomainServicesDirectoryServiceAccess)<p> | resources, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/aaddomainservicesdirectoryserviceaccess)|
| [AADDomainServicesLogonLogoff](/azure/azure-monitor/reference/tables/AADDomainServicesLogonLogoff)<p> | resources, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/aaddomainserviceslogonlogoff)|
| [AADDomainServicesPolicyChange](/azure/azure-monitor/reference/tables/AADDomainServicesPolicyChange)<p> | resources, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/aaddomainservicespolicychange)|
| [AADDomainServicesPrivilegeUse](/azure/azure-monitor/reference/tables/AADDomainServicesPrivilegeUse)<p> | resources, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/aaddomainservicesprivilegeuse)|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|

