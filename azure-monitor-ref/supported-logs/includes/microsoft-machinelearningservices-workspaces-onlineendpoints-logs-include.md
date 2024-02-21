---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/21/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.MachineLearningServices/workspaces/onlineEndpoints, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`AmlOnlineEndpointConsoleLog` |AmlOnlineEndpointConsoleLog |[AmlOnlineEndpointConsoleLog](/azure/azure-monitor/reference/tables/amlonlineendpointconsolelog)<p>Azure ML online endpoints console logs. It provides console logs output from user containers.|No|Yes|[Queries](/azure/azure-monitor/reference/queries/amlonlineendpointconsolelog)|Yes |
|`AmlOnlineEndpointEventLog` |AmlOnlineEndpointEventLog |[AmlOnlineEndpointEventLog](/azure/azure-monitor/reference/tables/amlonlineendpointeventlog)<p>Azure ML online endpoints event logs. It provides event logs regarding the inference-server container's life cycle.|No|No|[Queries](/azure/azure-monitor/reference/queries/amlonlineendpointeventlog)|Yes |
|`AmlOnlineEndpointTrafficLog` |AmlOnlineEndpointTrafficLog |[AmlOnlineEndpointTrafficLog](/azure/azure-monitor/reference/tables/amlonlineendpointtrafficlog)<p>Traffic logs for AzureML (machine learning) online endpoints. The table could be used to check the detailed information of the request to an online endpoint. For example, you could use it to check the request duration, the request failure reason, etc.|No|No|[Queries](/azure/azure-monitor/reference/queries/amlonlineendpointtrafficlog)|Yes |