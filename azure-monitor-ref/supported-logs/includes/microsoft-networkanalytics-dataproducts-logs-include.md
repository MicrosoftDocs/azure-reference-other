---
ms.service: azure-monitor
ms.topic: include
ms.date: 04/01/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.NetworkAnalytics/DataProducts, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`DatabaseQuery` |Database Query |[AOIDatabaseQuery](/azure/azure-monitor/reference/tables/aoidatabasequery)<p>Audit logs related to queries run on database, in dataproduct environment.|Yes|No|[Queries](/azure/azure-monitor/reference/queries/aoidatabasequery)|Yes |
|`Digestion` |Digestion |[AOIDigestion](/azure/azure-monitor/reference/tables/aoidigestion)<p>Logs related to digestion of files added to the input storage account. These can be used to verify that data is being successfully passed through to enrichment, or to troubleshoot issues with processing the raw data.|Yes|No|[Queries](/azure/azure-monitor/reference/queries/aoidigestion)|Yes |
|`Ingestion` |Ingestion |[AOIStorage](/azure/azure-monitor/reference/tables/aoistorage)<p>These are Audit logs related to ingestion of files on the input storage account.|Yes|No|[Queries](/azure/azure-monitor/reference/queries/aoistorage)|Yes |
|`IngestionDelete` |Delete ingested file ||No|No||Yes |
|`IngestionRead` |Read ingested file ||No|No||Yes |
|`ReadStorage` |Output storage read ||No|No||Yes |