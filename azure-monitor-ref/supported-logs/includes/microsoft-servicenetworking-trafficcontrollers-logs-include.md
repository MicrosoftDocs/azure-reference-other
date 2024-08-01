---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: Microsoft.ServiceNetworking/trafficControllers, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`TrafficControllerAccessLog` |Application Gateway for Containers Access Log |[AGCAccessLogs](/azure/azure-monitor/reference/tables/agcaccesslogs)<p>Contains details of client requests made to Application Gateway for Containers. Each client request creats a log entry that can be used to identify slow requests, determine error rates, and correlate logs with backend services.|Yes|No|[Queries](/azure/azure-monitor/reference/queries/agcaccesslogs)|Yes |