---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/01/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for nginx.nginxplus/nginxdeployments
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [NGXOperationLogs](/azure/azure-monitor/reference/tables/NGXOperationLogs)<p>NGINX access and error logs captured by NGINXaaS. | resources | LogManagement | Yes| [Yes](/azure/azure-monitor/reference/queries/ngxoperationlogs)|
| [NGXSecurityLogs](/azure/azure-monitor/reference/tables/NGXSecurityLogs)<p>NGINX security logs captured by NGINXaaS. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/ngxsecuritylogs)|

  
