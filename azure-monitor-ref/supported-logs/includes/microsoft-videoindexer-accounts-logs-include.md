---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: microsoft.videoindexer/accounts, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`Audit` |Audit |[VIAudit](/azure/azure-monitor/reference/tables/viaudit)<p>Audit logs from Video Indexer.|No|No|[Queries](/azure/azure-monitor/reference/queries/viaudit)|Yes |
|`IndexingLogs` |Indexing Logs |[VIIndexing](/azure/azure-monitor/reference/tables/viindexing)<p>Indexing logs from Video Indexer.|No|No|[Queries](/azure/azure-monitor/reference/queries/viindexing)|Yes |