---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/21/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Media/mediaservices/streamingEndpoints, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`StreamingEndpointRequests` |Streaming Endpoint Requests |[AMSStreamingEndpointRequests](/azure/azure-monitor/reference/tables/amsstreamingendpointrequests)<p>Contains information about requests to streaming endpoints. A streaming endpoint receives HTTP requests needed to stream video content. These requests usually come from video players or from the CDN.|Yes|No|[Queries](/azure/azure-monitor/reference/queries/amsstreamingendpointrequests)|Yes |