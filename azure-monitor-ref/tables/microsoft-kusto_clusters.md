---
title: Azure Monitor tables for microsoft.kusto/clusters
description: Azure Monitor tables for resource type microsoft.kusto/clusters
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
   
ms.date: 03/05/2024


---

# Resource log tables for microsoft.kusto/clusters  


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [ADXCommand](/azure/azure-monitor/reference/tables/ADXCommand)<p>Azure Data Explorer command execution summary. | undefined | LogManagement | No| -|
| [ADXIngestionBatching](/azure/azure-monitor/reference/tables/ADXIngestionBatching)<p>Azure Data Explorer ingestion batching operations. These logs have detailed statistics of batches ready for ingestion (duration, batch size and blobs count). | undefined | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/adxingestionbatching)|
| [ADXJournal](/azure/azure-monitor/reference/tables/ADXJournal)<p>Azure Data Explorer journal (metadata operations). | resources | LogManagement | No| -|
| [ADXQuery](/azure/azure-monitor/reference/tables/ADXQuery)<p>Azure Data Explorer query execution summary. | undefined | LogManagement | No| -|
| [ADXTableDetails](/azure/azure-monitor/reference/tables/ADXTableDetails)<p>Azure Data Explorer table details. | resources | LogManagement | No| -|
| [ADXTableUsageStatistics](/azure/azure-monitor/reference/tables/ADXTableUsageStatistics)<p>Azure Data Explorer table usage statistics. | undefined | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/adxtableusagestatistics)|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|
| [FailedIngestion](/azure/azure-monitor/reference/tables/FailedIngestion)<p>Failed ingestion operations logs provide detailed information about failed ingest operations. Logs include data source details, as well as error code and failure status (transient or permanent), that can be used for tracking the process of data source ingestion. Users can identify usage errors (permanent bad requests) and handle retries of transient failures. Ingestion logs are supported for queued ingestion to the ingestion endpoint using SDKs, data connections, and connectors. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/failedingestion)|
| [SucceededIngestion](/azure/azure-monitor/reference/tables/SucceededIngestion)<p>Succeeded ingestion operations logs provide information about successfully completed ingest operations. Logs include data source details that together with `Failed ingestion operations` logs can be used for tracking the process of ingestion of each data source. Ingestion logs are supported for queued ingestion to the ingestion endpoint using SDKs, data connections, and connectors. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/succeededingestion)|

