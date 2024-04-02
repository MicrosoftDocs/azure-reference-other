---
ms.service: azure-monitor
ms.topic: include
ms.date: 04/01/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: microsoft.botservice/botservices, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`BotRequest` |Requests from the channels to the bot |[ABSChannelToBotRequests](/azure/azure-monitor/reference/tables/abschanneltobotrequests)<p>All logs of requests from Azure Bot Service channels services to bots.|No|No||Yes |