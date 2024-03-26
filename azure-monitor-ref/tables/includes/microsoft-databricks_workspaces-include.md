---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.databricks/workspaces
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|
| [DatabricksAccounts](/azure/azure-monitor/reference/tables/DatabricksAccounts)<p>Databricks Accounts audit logs. | resources | LogManagement | No| -|
| [DatabricksBrickStoreHttpGateway](/azure/azure-monitor/reference/tables/DatabricksBrickStoreHttpGateway)<p>Contains Databricks Brick Store Http Gateway logs. | resources, audit | LogManagement | Yes| -|
| [DatabricksCloudStorageMetadata](/azure/azure-monitor/reference/tables/DatabricksCloudStorageMetadata)<p>Contains Databricks Cloud Storage Metadata logs. | resources, audit | LogManagement | Yes| -|
| [DatabricksClusters](/azure/azure-monitor/reference/tables/DatabricksClusters)<p>Databricks Clusters audit logs. | resources | LogManagement | No| -|
| [DatabricksDBFS](/azure/azure-monitor/reference/tables/DatabricksDBFS)<p>Databricks DBFS audit logs. | resources | LogManagement | No| -|
| [DatabricksDashboards](/azure/azure-monitor/reference/tables/DatabricksDashboards)<p>Contains Databricks Dashboards logs. | resources, audit | LogManagement | Yes| -|
| [DatabricksDataMonitoring](/azure/azure-monitor/reference/tables/DatabricksDataMonitoring)<p>Contains Databricks Data Monitoring logs. | resources, audit | LogManagement | Yes| -|
| [DatabricksDatabricksSQL](/azure/azure-monitor/reference/tables/DatabricksDatabricksSQL)<p>Databricks databrickssql audit logs. | resources | LogManagement | No| -|
| [DatabricksFeatureStore](/azure/azure-monitor/reference/tables/DatabricksFeatureStore)<p>Audit logs for events related to Databricks ML Feature Store operations. | resources | LogManagement | No| -|
| [DatabricksFilesystem](/azure/azure-monitor/reference/tables/DatabricksFilesystem)<p>Contains Databricks Filesystem logs. | resources, audit | LogManagement | Yes| -|
| [DatabricksGenie](/azure/azure-monitor/reference/tables/DatabricksGenie)<p>Audit logs for Databricks workspaces customer support access events. | resources | LogManagement | No| -|
| [DatabricksGitCredentials](/azure/azure-monitor/reference/tables/DatabricksGitCredentials)<p>Databricks Git credentials audit logs. | resources | LogManagement | No| -|
| [DatabricksGlobalInitScripts](/azure/azure-monitor/reference/tables/DatabricksGlobalInitScripts)<p>Audit logs for events related to creation, modification etc. of Databricks cluster global init scripts. | resources | LogManagement | No| -|
| [DatabricksIAMRole](/azure/azure-monitor/reference/tables/DatabricksIAMRole)<p>Audit logs for events of changing IAM role ACLs. | resources | LogManagement | No| -|
| [DatabricksIngestion](/azure/azure-monitor/reference/tables/DatabricksIngestion)<p>Contains Databricks Ingestion logs. | resources, audit | LogManagement | Yes| -|
| [DatabricksInstancePools](/azure/azure-monitor/reference/tables/DatabricksInstancePools)<p>Databricks Instance Pools audit logs. | resources | LogManagement | No| -|
| [DatabricksJobs](/azure/azure-monitor/reference/tables/DatabricksJobs)<p>Databricks Jobs audit logs. | resources | LogManagement | No| -|
| [DatabricksLineageTracking](/azure/azure-monitor/reference/tables/DatabricksLineageTracking)<p>Contains Databricks Lineage Tracking logs. | resources, audit | LogManagement | Yes| -|
| [DatabricksMLflowAcledArtifact](/azure/azure-monitor/reference/tables/DatabricksMLflowAcledArtifact)<p>Audit logs for events of reading and writing Databricks MLflow ACLed artifacts. | resources | LogManagement | No| -|
| [DatabricksMLflowExperiment](/azure/azure-monitor/reference/tables/DatabricksMLflowExperiment)<p>Audit logs for events related to manipulation of Databricks MLflow experiments. | resources | LogManagement | No| -|
| [DatabricksMarketplaceConsumer](/azure/azure-monitor/reference/tables/DatabricksMarketplaceConsumer)<p>Contains Databricks Marketplace Consumer logs. | resources, audit | LogManagement | Yes| -|
| [DatabricksNotebook](/azure/azure-monitor/reference/tables/DatabricksNotebook)<p>Databricks Notebook audit logs. | resources | LogManagement | No| -|
| [DatabricksPredictiveOptimization](/azure/azure-monitor/reference/tables/DatabricksPredictiveOptimization)<p>Contains Databricks Predictive Optimization logs. | resources, audit | LogManagement | Yes| -|
| [DatabricksRemoteHistoryService](/azure/azure-monitor/reference/tables/DatabricksRemoteHistoryService)<p>Audit logs for events adding and deleting credentials for Databricks remote history service. | resources | LogManagement | No| -|
| [DatabricksSQL](/azure/azure-monitor/reference/tables/DatabricksSQL)<p>Audit logs for events related to creation, modification etc. of Databricks SQL endpoints. | undefined | LogManagement | No| -|
| [DatabricksSQLPermissions](/azure/azure-monitor/reference/tables/DatabricksSQLPermissions)<p>Databricks SQL Permissions audit logs. | resources | LogManagement | No| -|
| [DatabricksSSH](/azure/azure-monitor/reference/tables/DatabricksSSH)<p>Databricks SSH audit logs. | resources | LogManagement | No| -|
| [DatabricksSecrets](/azure/azure-monitor/reference/tables/DatabricksSecrets)<p>Databricks Secrets audit logs. | resources | LogManagement | No| -|
| [DatabricksWebTerminal](/azure/azure-monitor/reference/tables/DatabricksWebTerminal)<p>Databricks web terminal audit logs. | resources | LogManagement | No| -|
| [DatabricksWorkspace](/azure/azure-monitor/reference/tables/DatabricksWorkspace)<p>Databricks Workspace audit logs. | resources | LogManagement | No| -|

  
