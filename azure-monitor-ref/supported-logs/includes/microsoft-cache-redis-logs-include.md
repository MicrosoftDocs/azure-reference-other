---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Cache/redis, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`ConnectedClientList` |Connected client list |[ACRConnectedClientList](/azure/azure-monitor/reference/tables/acrconnectedclientlist)<p>Logs count of Redis clients connected to a cache instance and their IP addresses, logged at a 10-second interval.|Yes|No|[Queries](/azure/azure-monitor/reference/queries/acrconnectedclientlist)|Yes |
|`MSEntraAuthenticationAuditLog` |MSEntra authentication audit log ||No|No||Yes |