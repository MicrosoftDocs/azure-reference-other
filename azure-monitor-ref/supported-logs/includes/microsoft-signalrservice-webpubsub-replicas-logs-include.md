---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/05/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.SignalRService/WebPubSub/replicas, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`ConnectivityLogs` |Connectivity logs for Azure Web PubSub Service. |[WebPubSubConnectivity](/azure/azure-monitor/reference/tables/webpubsubconnectivity)<p>Connectivity logs provide detailed information for Azure Web PubSub hub connections. For example, basic information (user ID, connection ID, and so on) and event information (connect, disconnect, and abort event, and so on) and can be used to troubleshoot connection-related issues.|No|Yes||Yes |
|`HttpRequestLogs` |Http Request logs for Azure Web PubSub Service. |[WebPubSubHttpRequest](/azure/azure-monitor/reference/tables/webpubsubhttprequest)<p>Http request logs provide detailed information for the http requests received by Azure Web PubSub. For example, status code and url of the request and is helpful to troubleshoot request-related issues.|No|Yes||Yes |
|`MessagingLogs` |Messaging logs for Azure Web PubSub Service. ||No|Yes||Yes |