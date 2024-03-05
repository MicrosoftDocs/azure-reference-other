---
title: Azure Monitor tables for microsoft.synapse/workspaces
description: Azure Monitor tables for resource type microsoft.synapse/workspaces
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
   
ms.date: 03/05/2024


---

# Resource log tables for microsoft.synapse/workspaces  


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|
| [SQLSecurityAuditEvents](/azure/azure-monitor/reference/tables/SQLSecurityAuditEvents)<p>Azure Synapse SQL Audit Log. | resources | LogManagement | No| -|
| [SynapseBigDataPoolApplicationsEnded](/azure/azure-monitor/reference/tables/SynapseBigDataPoolApplicationsEnded)<p>Information about ended Apache Spark applications. | resources | LogManagement | No| -|
| [SynapseBuiltinSqlPoolRequestsEnded](/azure/azure-monitor/reference/tables/SynapseBuiltinSqlPoolRequestsEnded)<p>Ended Azure Synapse built-in serverless SQL requests. | resources | LogManagement | No| -|
| [SynapseDXCommand](/azure/azure-monitor/reference/tables/SynapseDXCommand)<p>Azure data explorer synapse command execution summary. Logs include DatabaseName, State, Duration that can be used for monitoring the commands which were invoked on the cluster | resources | LogManagement | No| -|
| [SynapseDXFailedIngestion](/azure/azure-monitor/reference/tables/SynapseDXFailedIngestion)<p>Failed ingestion operations logs provide detailed information about failed ingest operations. Logs include data source details, as well as error code and failure status (transient or permanent), that can be used for tracking the process of data source ingestion. Users can identify usage errors (permanent bad requests) and handle retries of transient failures. Ingestion logs are supported for queued ingestion to the ingestion endpoint using SDKs, data connections, and connectors | resources | LogManagement | No| -|
| [SynapseDXIngestionBatching](/azure/azure-monitor/reference/tables/SynapseDXIngestionBatching)<p>Azure data explore synapse ingestion batching operations. These logs have detailed statistics of batches ready for ingestion (duration, batch size and blobs count) | resources | LogManagement | No| -|
| [SynapseDXQuery](/azure/azure-monitor/reference/tables/SynapseDXQuery)<p>Azure data explorer synpase query execution summary. Logs include DatabaseName, State, Duration that can be used for monitoring the queries which were invoked on the cluster | resources | LogManagement | No| -|
| [SynapseDXSucceededIngestion](/azure/azure-monitor/reference/tables/SynapseDXSucceededIngestion)<p>Succeeded ingestion operations logs provide information about successfully completed ingest operations. Logs include data source details that together with `Failed ingestion operations` logs can be used for tracking the process of ingestion of each data source. Ingestion logs are supported for queued ingestion to the ingestion endpoint using SDKs, data connections, and connectors | resources | LogManagement | No| -|
| [SynapseDXTableDetails](/azure/azure-monitor/reference/tables/SynapseDXTableDetails)<p>Azure Data Explorer Synpase table details | resources | LogManagement | No| -|
| [SynapseDXTableUsageStatistics](/azure/azure-monitor/reference/tables/SynapseDXTableUsageStatistics)<p>Azure date explorer synapse table usage statistics. Logs include DatabaseName, TableName, User that can be used for monitoring cluster's table usage | resources | LogManagement | No| -|
| [SynapseGatewayApiRequests](/azure/azure-monitor/reference/tables/SynapseGatewayApiRequests)<p>Azure Synapse gateway API requests. | resources | LogManagement | No| -|
| [SynapseIntegrationActivityRuns](/azure/azure-monitor/reference/tables/SynapseIntegrationActivityRuns)<p>Logs for Synapse integration activity runs. | resources | LogManagement | No| -|
| [SynapseIntegrationPipelineRuns](/azure/azure-monitor/reference/tables/SynapseIntegrationPipelineRuns)<p>Logs for Synapse integration pipeline runs. | resources | LogManagement | No| -|
| [SynapseIntegrationTriggerRuns](/azure/azure-monitor/reference/tables/SynapseIntegrationTriggerRuns)<p>Logs for Synapse integration trigger runs. | resources | LogManagement | No| -|
| [SynapseLinkEvent](/azure/azure-monitor/reference/tables/SynapseLinkEvent)<p>Information about Synapse Link, including Link status and Link table status. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/synapselinkevent)|
| [SynapseRbacOperations](/azure/azure-monitor/reference/tables/SynapseRbacOperations)<p>Azure Synapse role-based access control (SRBAC) operations. | resources | LogManagement | No| -|
| [SynapseScopePoolScopeJobsEnded](/azure/azure-monitor/reference/tables/SynapseScopePoolScopeJobsEnded)<p>SCOPE ended event including SCOPE job result and Information about the job. | resources | LogManagement | No| -|
| [SynapseScopePoolScopeJobsStateChange](/azure/azure-monitor/reference/tables/SynapseScopePoolScopeJobsStateChange)<p>SCOPE job state change event. | resources | LogManagement | No| -|
| [SynapseSqlPoolDmsWorkers](/azure/azure-monitor/reference/tables/SynapseSqlPoolDmsWorkers)<p>Information about workers completing DMS steps in an Azure Synapse dedicated SQL pool. | resources | LogManagement | Yes| -|
| [SynapseSqlPoolExecRequests](/azure/azure-monitor/reference/tables/SynapseSqlPoolExecRequests)<p>Information about SQL requests or queries in an Azure Synapse dedicated SQL pool. | resources | LogManagement | Yes| -|
| [SynapseSqlPoolRequestSteps](/azure/azure-monitor/reference/tables/SynapseSqlPoolRequestSteps)<p>Information about request steps that compose a given SQL request or query in an Azure Synapse dedicated SQL pool. | resources | LogManagement | Yes| -|
| [SynapseSqlPoolSqlRequests](/azure/azure-monitor/reference/tables/SynapseSqlPoolSqlRequests)<p>Information about query distributions of the steps of SQL requests/queries in an Azure Synapse dedicated SQL pool. | resources | LogManagement | Yes| -|
| [SynapseSqlPoolWaits](/azure/azure-monitor/reference/tables/SynapseSqlPoolWaits)<p>Information about the wait states encountered during execution of a SQL request/query in an Azure Synapse dedicated SQL pool, including locks and waits on transmission queues. | resources | LogManagement | Yes| -|

