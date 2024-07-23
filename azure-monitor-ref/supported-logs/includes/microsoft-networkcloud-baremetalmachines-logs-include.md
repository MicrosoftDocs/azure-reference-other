---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/23/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.NetworkCloud/bareMetalMachines, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`DefenderSecurity` |Security - Defender |[NCBMSecurityDefenderLogs](/azure/azure-monitor/reference/tables/ncbmsecuritydefenderlogs)<p>Security log events on Nexus Baremetal Machines to monitor and detect user access to the system.|Yes|No||Yes |
|`NexusBreakGlassAudit` |Security - Break Glass Audit |[NCBMBreakGlassAuditLogs](/azure/azure-monitor/reference/tables/ncbmbreakglassauditlogs)<p>Security log events on Nexus Baremetal Machines to monitor and detect user access to the system.|Yes|No||Yes |
|`SecurityCritical` |Security - Critical ||No|No||Yes |
|`SecurityDebug` |Security - Debug |[NCBMSecurityLogs](/azure/azure-monitor/reference/tables/ncbmsecuritylogs)<p>Security log events on Nexus Baremetal Machines to monitor and detect user access to the system.|Yes|No||Yes |
|`SecurityError` |Security - Error |[NCBMSecurityLogs](/azure/azure-monitor/reference/tables/ncbmsecuritylogs)<p>Security log events on Nexus Baremetal Machines to monitor and detect user access to the system.|Yes|No||Yes |
|`SecurityInfo` |Security - Info |[NCBMSecurityLogs](/azure/azure-monitor/reference/tables/ncbmsecuritylogs)<p>Security log events on Nexus Baremetal Machines to monitor and detect user access to the system.|Yes|No||Yes |
|`SecurityNotice` |Security - Notice |[NCBMSecurityLogs](/azure/azure-monitor/reference/tables/ncbmsecuritylogs)<p>Security log events on Nexus Baremetal Machines to monitor and detect user access to the system.|Yes|No||Yes |
|`SecurityWarning` |Security - Warning ||No|No||Yes |
|`SyslogCritical` |System - Critical |[NCBMSystemLogs](/azure/azure-monitor/reference/tables/ncbmsystemlogs)<p>Syslog events on Nexus Baremetal Machines providing critical insights into system activities, errors and anomalies for effecient troubleshooting and monitoring.|Yes|No||Yes |
|`SyslogDebug` |System - Debug |[NCBMSystemLogs](/azure/azure-monitor/reference/tables/ncbmsystemlogs)<p>Syslog events on Nexus Baremetal Machines providing critical insights into system activities, errors and anomalies for effecient troubleshooting and monitoring.|Yes|No||Yes |
|`SyslogError` |System - Error |[NCBMSystemLogs](/azure/azure-monitor/reference/tables/ncbmsystemlogs)<p>Syslog events on Nexus Baremetal Machines providing critical insights into system activities, errors and anomalies for effecient troubleshooting and monitoring.|Yes|No||Yes |
|`SyslogInfo` |System - Info |[NCBMSystemLogs](/azure/azure-monitor/reference/tables/ncbmsystemlogs)<p>Syslog events on Nexus Baremetal Machines providing critical insights into system activities, errors and anomalies for effecient troubleshooting and monitoring.|Yes|No||Yes |
|`SyslogNotice` |System - Notice |[NCBMSystemLogs](/azure/azure-monitor/reference/tables/ncbmsystemlogs)<p>Syslog events on Nexus Baremetal Machines providing critical insights into system activities, errors and anomalies for effecient troubleshooting and monitoring.|Yes|No||Yes |
|`SyslogWarning` |System - Warning |[NCBMSystemLogs](/azure/azure-monitor/reference/tables/ncbmsystemlogs)<p>Syslog events on Nexus Baremetal Machines providing critical insights into system activities, errors and anomalies for effecient troubleshooting and monitoring.|Yes|No||Yes |