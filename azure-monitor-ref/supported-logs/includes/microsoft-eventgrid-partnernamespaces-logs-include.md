---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: Microsoft.EventGrid/partnerNamespaces, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`DataPlaneRequests` |Data plane operations logs |[AegDataPlaneRequests](/azure/azure-monitor/reference/tables/aegdataplanerequests)<p>Logs for Event Grid data plane requests (publish and options) against a topic/domain/partnernamespace. It can be used for auditing purposes. Logs are aggregated over a minute and displays the total number of requests with specific request properties.|No|No|[Queries](/azure/azure-monitor/reference/queries/aegdataplanerequests)|Yes |
|`PublishFailures` |Publish Failure Logs ||No|No||No |