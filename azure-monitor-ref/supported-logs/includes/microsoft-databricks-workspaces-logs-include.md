---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Databricks/workspaces, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`accounts` |Databricks Accounts |[DatabricksAccounts](/azure/azure-monitor/reference/tables/databricksaccounts)<p>Databricks Accounts audit logs.|No|Yes||No |
|`BrickStoreHttpGateway` |Databricks Brick Store HttpGateway ||No|Yes||Yes |
|`capsule8Dataplane` |Databricks Capsule8 Container Security Scanning Reports |[DatabricksCapsule8Dataplane](/azure/azure-monitor/reference/tables/databrickscapsule8dataplane)<p>Audit logs for Databricks service capsule8-alerts-dataplane.|No|No||Yes |
|`clamAVScan` |Databricks Clam AV Scan |[DatabricksClamAVScan](/azure/azure-monitor/reference/tables/databricksclamavscan)<p>Audit logs for Databricks clamav scan service|No|No||Yes |
|`CloudStorageMetadata` |Databricks Cloud Storage Metadata ||No|No||Yes |
|`clusterLibraries` |Databricks Cluster Libraries |[DatabricksClusterLibraries](/azure/azure-monitor/reference/tables/databricksclusterlibraries)<p>Audit logs for actions taken on cluster libraries in Databricks.|No|No||Yes |
|`clusters` |Databricks Clusters |[DatabricksClusters](/azure/azure-monitor/reference/tables/databricksclusters)<p>Databricks Clusters audit logs.|No|Yes||No |
|`Dashboards` |Databricks Dashboards ||No|Yes||Yes |
|`databrickssql` |Databricks DatabricksSQL |[DatabricksSQL](/azure/azure-monitor/reference/tables/databrickssql)<p>Audit logs for events related to creation, modification etc. of Databricks SQL endpoints.|No|No||Yes |
|`DataMonitoring` |Databricks Data Monitoring ||No|No||Yes |
|`dbfs` |Databricks File System |[DatabricksDBFS](/azure/azure-monitor/reference/tables/databricksdbfs)<p>Databricks DBFS audit logs.|No|Yes||No |
|`deltaPipelines` |Databricks Delta Pipelines |[DatabricksDeltaPipelines](/azure/azure-monitor/reference/tables/databricksdeltapipelines)<p>Databricks delta pipelines audit logs.|No|No||Yes |
|`featureStore` |Databricks Feature Store |[DatabricksFeatureStore](/azure/azure-monitor/reference/tables/databricksfeaturestore)<p>Audit logs for events related to Databricks ML Feature Store operations.|No|Yes||Yes |
|`genie` |Databricks Genie |[DatabricksGenie](/azure/azure-monitor/reference/tables/databricksgenie)<p>Audit logs for Databricks workspaces customer support access events.|No|Yes||Yes |
|`gitCredentials` |Databricks Git Credentials |[DatabricksGitCredentials](/azure/azure-monitor/reference/tables/databricksgitcredentials)<p>Databricks Git credentials audit logs.|No|No||Yes |
|`globalInitScripts` |Databricks Global Init Scripts |[DatabricksGlobalInitScripts](/azure/azure-monitor/reference/tables/databricksglobalinitscripts)<p>Audit logs for events related to creation, modification etc. of Databricks cluster global init scripts.|No|Yes||Yes |
|`iamRole` |Databricks IAM Role |[DatabricksIAMRole](/azure/azure-monitor/reference/tables/databricksiamrole)<p>Audit logs for events of changing IAM role ACLs.|No|No||Yes |
|`Ingestion` |Databricks Ingestion ||No|No||Yes |
|`instancePools` |Instance Pools |[DatabricksInstancePools](/azure/azure-monitor/reference/tables/databricksinstancepools)<p>Databricks Instance Pools audit logs.|No|Yes||No |
|`jobs` |Databricks Jobs |[DatabricksJobs](/azure/azure-monitor/reference/tables/databricksjobs)<p>Databricks Jobs audit logs.|No|Yes||No |
|`LineageTracking` |Databricks Lineage Tracking ||No|Yes||Yes |
|`MarketplaceConsumer` |Databricks Marketplace Consumer ||No|Yes||Yes |
|`mlflowAcledArtifact` |Databricks MLFlow Acled Artifact |[DatabricksMLflowAcledArtifact](/azure/azure-monitor/reference/tables/databricksmlflowacledartifact)<p>Audit logs for events of reading and writing Databricks MLflow ACLed artifacts.|No|Yes||Yes |
|`mlflowExperiment` |Databricks MLFlow Experiment |[DatabricksMLflowExperiment](/azure/azure-monitor/reference/tables/databricksmlflowexperiment)<p>Audit logs for events related to manipulation of Databricks MLflow experiments.|No|Yes||Yes |
|`modelRegistry` |Databricks Model Registry |[DatabricksModelRegistry](/azure/azure-monitor/reference/tables/databricksmodelregistry)<p>Databricks model registry audit logs.|No|No||Yes |
|`notebook` |Databricks Notebook |[DatabricksNotebook](/azure/azure-monitor/reference/tables/databricksnotebook)<p>Databricks Notebook audit logs.|No|Yes||No |
|`partnerHub` |Databricks Partner Hub |[DatabricksPartnerHub](/azure/azure-monitor/reference/tables/databrickspartnerhub)<p>Audit logs for Databricks partner hub service.|No|No||Yes |
|`PredictiveOptimization` |Databricks Predictive Optimization ||No|No||Yes |
|`RemoteHistoryService` |Databricks Remote History Service |[DatabricksRemoteHistoryService](/azure/azure-monitor/reference/tables/databricksremotehistoryservice)<p>Audit logs for events adding and deleting credentials for Databricks remote history service.|No|Yes||Yes |
|`repos` |Databricks Repos |[DatabricksRepos](/azure/azure-monitor/reference/tables/databricksrepos)<p>Databricks repos audit logs.|No|No||Yes |
|`secrets` |Databricks Secrets |[DatabricksSecrets](/azure/azure-monitor/reference/tables/databrickssecrets)<p>Databricks Secrets audit logs.|No|Yes||No |
|`serverlessRealTimeInference` |Databricks Serverless Real-Time Inference |[DatabricksServerlessRealTimeInference](/azure/azure-monitor/reference/tables/databricksserverlessrealtimeinference)<p>Audit logs from Databricks model serving v2 API service.|No|No||Yes |
|`sqlanalytics` |Databricks SQL Analytics ||No|No||Yes |
|`sqlPermissions` |Databricks SQLPermissions |[DatabricksSQLPermissions](/azure/azure-monitor/reference/tables/databrickssqlpermissions)<p>Databricks SQL Permissions audit logs.|No|Yes||No |
|`ssh` |Databricks SSH |[DatabricksSSH](/azure/azure-monitor/reference/tables/databricksssh)<p>Databricks SSH audit logs.|No|Yes||No |
|`unityCatalog` |Databricks Unity Catalog |[DatabricksUnityCatalog](/azure/azure-monitor/reference/tables/databricksunitycatalog)<p>Databricks unity catalog audit logs.|No|No||Yes |
|`webTerminal` |Databricks Web Terminal |[DatabricksWebTerminal](/azure/azure-monitor/reference/tables/databrickswebterminal)<p>Databricks web terminal audit logs.|No|No||Yes |
|`workspace` |Databricks Workspace |[DatabricksWorkspace](/azure/azure-monitor/reference/tables/databricksworkspace)<p>Databricks Workspace audit logs.|No|Yes||No |