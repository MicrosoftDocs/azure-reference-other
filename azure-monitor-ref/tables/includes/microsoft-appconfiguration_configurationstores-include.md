---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.appconfiguration/configurationstores
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AACAudit](/azure/azure-monitor/reference/tables/AACAudit)<p>Azure App Configuration audit logs. | audit | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/aacaudit)|
| [AACHttpRequest](/azure/azure-monitor/reference/tables/AACHttpRequest)<p>Incoming requests to Azure App Configuration. The records in this table are aggregated. The 'HitCount' field describes the number of requests that each record accounts for. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/aachttprequest)|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|

  
