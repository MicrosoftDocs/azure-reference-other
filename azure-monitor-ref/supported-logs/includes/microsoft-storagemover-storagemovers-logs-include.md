---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: Microsoft.StorageMover/storageMovers, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`CopyLogsFailed` |Copy logs - Failed |[StorageMoverCopyLogsFailed](/azure/azure-monitor/reference/tables/storagemovercopylogsfailed)<p>The result logs generated during the execution of Storage Mover job runs where the transfer result is 'Failed'. The logs include the details of the scanned items and their transfer result.|Yes|No||Yes |
|`JobRunLogs` |Job run logs |[StorageMoverJobRunLogs](/azure/azure-monitor/reference/tables/storagemoverjobrunlogs)<p>Logs associated with Storage Mover job runs.|Yes|No||Yes |