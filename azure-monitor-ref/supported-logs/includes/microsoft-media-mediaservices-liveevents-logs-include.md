---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Media/mediaservices/liveEvents, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`LiveEventState` |Live Event Operations |[AMSLiveEventOperations](/azure/azure-monitor/reference/tables/amsliveeventoperations)<p>Contains logs related to a Live Event. Logs are sent when an encoder connects, disconnects, or if there is a discontinuity in the media data.|Yes|No|[Queries](../../queries/amsliveeventoperations.md)|Yes |