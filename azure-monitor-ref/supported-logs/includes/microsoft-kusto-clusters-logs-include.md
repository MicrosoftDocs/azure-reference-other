---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Kusto/clusters, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`Command` |Command |[ADXCommand](/azure/azure-monitor/reference/tables/adxcommand)<p>Azure Data Explorer command execution summary.|No|Yes||No |
|`FailedIngestion` |Failed ingestion |[FailedIngestion](/azure/azure-monitor/reference/tables/failedingestion)<p>Failed ingestion operations logs provide detailed information about failed ingest operations. Logs include data source details, as well as error code and failure status (transient or permanent), that can be used for tracking the process of data source ingestion. Users can identify usage errors (permanent bad requests) and handle retries of transient failures. Ingestion logs are supported for queued ingestion to the ingestion endpoint using SDKs, data connections, and connectors.|No|Yes|[Queries](../../queries/failedingestion.md)|No |
|`IngestionBatching` |Ingestion batching |[ADXIngestionBatching](/azure/azure-monitor/reference/tables/adxingestionbatching)<p>Azure Data Explorer ingestion batching operations. These logs have detailed statistics of batches ready for ingestion (duration, batch size and blobs count).|No|No|[Queries](../../queries/adxingestionbatching.md)|No |
|`Journal` |Journal |[ADXJournal](/azure/azure-monitor/reference/tables/adxjournal)<p>Azure Data Explorer journal (metadata operations).|No|Yes||Yes |
|`Query` |Query |[ADXQuery](/azure/azure-monitor/reference/tables/adxquery)<p>Azure Data Explorer query execution summary.|No|Yes||No |
|`SucceededIngestion` |Succeeded ingestion |[SucceededIngestion](/azure/azure-monitor/reference/tables/succeededingestion)<p>Succeeded ingestion operations logs provide information about successfully completed ingest operations. Logs include data source details that together with `Failed ingestion operations` logs can be used for tracking the process of ingestion of each data source. Ingestion logs are supported for queued ingestion to the ingestion endpoint using SDKs, data connections, and connectors.|No|Yes|[Queries](../../queries/succeededingestion.md)|No |
|`TableDetails` |Table details |[ADXTableDetails](/azure/azure-monitor/reference/tables/adxtabledetails)<p>Azure Data Explorer table details.|No|Yes||No |
|`TableUsageStatistics` |Table usage statistics |[ADXTableUsageStatistics](/azure/azure-monitor/reference/tables/adxtableusagestatistics)<p>Azure Data Explorer table usage statistics.|No|Yes|[Queries](../../queries/adxtableusagestatistics.md)|No |