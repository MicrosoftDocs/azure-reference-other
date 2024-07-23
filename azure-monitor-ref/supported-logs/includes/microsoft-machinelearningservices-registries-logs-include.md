---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/23/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.MachineLearningServices/registries, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`RegistryAssetReadEvent` |Registry Asset Read Event ||No|No||Yes |
|`RegistryAssetWriteEvent` |Registry Asset Write Event |[AmlRegistryWriteEventsLog](/azure/azure-monitor/reference/tables/amlregistrywriteeventslog)<p>Azure ML Registry Write events log. It keeps records of Write operations with registries data access (data plane), including user identity, asset name and version for each access event.|No|No|[Queries](/azure/azure-monitor/reference/queries/amlregistrywriteeventslog)|Yes |