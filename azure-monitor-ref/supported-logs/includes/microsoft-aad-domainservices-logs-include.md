---
ms.service: azure-monitor
ms.topic: include
ms.date: 08/08/2024
ms.author: orens
author: osalzberg
ms.custom: Microsoft.AAD/DomainServices, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`AccountLogon` |AccountLogon |[AADDomainServicesAccountLogon](/azure/azure-monitor/reference/tables/aaddomainservicesaccountlogon)|No|Yes|[Queries](/azure/azure-monitor/reference/queries/aaddomainservicesaccountlogon)|No |
|`AccountManagement` |AccountManagement |[AADDomainServicesAccountManagement](/azure/azure-monitor/reference/tables/aaddomainservicesaccountmanagement)|No|Yes|[Queries](/azure/azure-monitor/reference/queries/aaddomainservicesaccountmanagement)|No |
|`DetailTracking` |DetailTracking ||No|No||No |
|`DirectoryServiceAccess` |DirectoryServiceAccess |[AADDomainServicesDirectoryServiceAccess](/azure/azure-monitor/reference/tables/aaddomainservicesdirectoryserviceaccess)|No|Yes|[Queries](/azure/azure-monitor/reference/queries/aaddomainservicesdirectoryserviceaccess)|No |
|`DNSServerAuditsDynamicUpdates` |DNSServerAuditsDynamicUpdates - Preview |[AADDomainServicesDNSAuditsDynamicUpdates](/azure/azure-monitor/reference/tables/aaddomainservicesdnsauditsdynamicupdates)<p>DNS server audit events enable change tracking on the DNS server. This table contains operational audit events for dynamic updates.|Yes|No||Yes |
|`DNSServerAuditsGeneral` |DNSServerAuditsGeneral - Preview |[AADDomainServicesDNSAuditsGeneral](/azure/azure-monitor/reference/tables/aaddomainservicesdnsauditsgeneral)<p>DNS server audit events enable change tracking on the DNS server. An audit event is logged each time server, zone, or resource record settings are changed. This includes operational events such as zone transfers, and DNSSEC zone signing and unsigning. This table captures audit events that are not from dynamic updates.|Yes|No||Yes |
|`LogonLogoff` |LogonLogoff |[AADDomainServicesLogonLogoff](/azure/azure-monitor/reference/tables/aaddomainserviceslogonlogoff)|No|Yes|[Queries](/azure/azure-monitor/reference/queries/aaddomainserviceslogonlogoff)|No |
|`ObjectAccess` |ObjectAccess ||No|No||No |
|`PolicyChange` |PolicyChange |[AADDomainServicesPolicyChange](/azure/azure-monitor/reference/tables/aaddomainservicespolicychange)|No|Yes|[Queries](/azure/azure-monitor/reference/queries/aaddomainservicespolicychange)|No |
|`PrivilegeUse` |PrivilegeUse |[AADDomainServicesPrivilegeUse](/azure/azure-monitor/reference/tables/aaddomainservicesprivilegeuse)|No|Yes|[Queries](/azure/azure-monitor/reference/queries/aaddomainservicesprivilegeuse)|No |
|`SystemSecurity` |SystemSecurity ||No|No||No |