---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/05/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.StorageCache/caches, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`AscCacheOperationEvent` |HPC Cache operation event |[StorageCacheOperationEvents](/azure/azure-monitor/reference/tables/storagecacheoperationevents)<p>Logs for Azure HPC Cache API requests.|No|No|[Queries](/azure/azure-monitor/reference/queries/storagecacheoperationevents)|Yes |
|`AscUpgradeEvent` |HPC Cache upgrade event ||No|No||Yes |
|`AscWarningEvent` |HPC Cache warning |[StorageCacheWarningEvents](/azure/azure-monitor/reference/tables/storagecachewarningevents)<p>Logs for Azure HPC Cache warning events.|No|No|[Queries](/azure/azure-monitor/reference/queries/storagecachewarningevents)|Yes |