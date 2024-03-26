---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.botservice/botservices
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [ABSBotRequests](/azure/azure-monitor/reference/tables/ABSBotRequests)<p>Logs of requests made by Azure Bot Service onbehalf of a bot such as requests from channel to bot and to other dependencies. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/absbotrequests)|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|

  
