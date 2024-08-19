---
title: Azure Monitor Resource log / log analytics tables
description: Field definitions for Azure Monitor resource log / log analytics tables.
author: EdB-MSFT
ms.topic: reference
ms.service: azure-monitor
ms.date: 08/19/2024
ms.author: edbaynash
ms.reviewer: lualderm

---

# Azure Monitor Resource log / log analytics tables

[Azure Monitor resource logs](/azure/azure-monitor/essentials/platform-logs-overview) are logs emitted by Azure services that describe the operation of those services or resources. All resource logs available through Azure Monitor share a common top-level schema. Each service has the flexibility to emit unique properties for its own events. When exported to a [Log Analytics workspace](/azure/azure-monitor/logs/log-analytics-workspace-overview) the logs are stored in tables. This set of articles contains field definitions for the log analytics tables. The table definitions are also available in the Log Analytics workspace.  

## Resource log / log analytics tables


### Analysis Services  

microsoft.analysisservices/servers  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AzureDiagnostics](azurediagnostics.md)

### API Management services  

Microsoft.ApiManagement/service  

- [APIMDevPortalAuditDiagnosticLog](apimdevportalauditdiagnosticlog.md)
- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AzureDiagnostics](azurediagnostics.md)
- [ApiManagementGatewayLogs](apimanagementgatewaylogs.md)
- [ApiManagementWebSocketConnectionLogs](apimanagementwebsocketconnectionlogs.md)

### App Services  

Microsoft.Web/sites  

- [AzureActivity](azureactivity.md)
- [LogicAppWorkflowRuntime](logicappworkflowruntime.md)
- [AppServiceAuthenticationLogs](appserviceauthenticationlogs.md)
- [AppServiceServerlessSecurityPluginData](appserviceserverlesssecurityplugindata.md)
- [AzureMetrics](azuremetrics.md)
- [AppServiceAppLogs](appserviceapplogs.md)
- [AppServiceAuditLogs](appserviceauditlogs.md)
- [AppServiceConsoleLogs](appserviceconsolelogs.md)
- [AppServiceFileAuditLogs](appservicefileauditlogs.md)
- [AppServiceHTTPLogs](appservicehttplogs.md)
- [FunctionAppLogs](functionapplogs.md)
- [AppServicePlatformLogs](appserviceplatformlogs.md)
- [AppServiceIPSecAuditLogs](appserviceipsecauditlogs.md)

### Application Gateway for Containers  

Microsoft.ServiceNetworking/TrafficControllers  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AGCAccessLogs](agcaccesslogs.md)

### Application Gateways  

Microsoft.Network/applicationGateways  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AGWAccessLogs](agwaccesslogs.md)
- [AGWPerformanceLogs](agwperformancelogs.md)
- [AGWFirewallLogs](agwfirewalllogs.md)
- [AzureDiagnostics](azurediagnostics.md)

### Application Insights  

microsoft.insights/components  

- [AzureActivity](azureactivity.md)
- [AppAvailabilityResults](appavailabilityresults.md)
- [AppBrowserTimings](appbrowsertimings.md)
- [AppDependencies](appdependencies.md)
- [AppEvents](appevents.md)
- [AppMetrics](appmetrics.md)
- [AppPageViews](apppageviews.md)
- [AppPerformanceCounters](appperformancecounters.md)
- [AppRequests](apprequests.md)
- [AppSystemEvents](appsystemevents.md)
- [AppTraces](apptraces.md)
- [AppExceptions](appexceptions.md)

### Automation account  

Microsoft.Automation/AutomationAccounts  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AzureDiagnostics](azurediagnostics.md)
- [Heartbeat](heartbeat.md)
- [Update](update.md)
- [UpdateSummary](updatesummary.md)
- [UpdateRunProgress](updaterunprogress.md)

### AVS Private Cloud  

microsoft.avs/privateClouds  

- [AVSSyslog](avssyslog.md)

### Azure Active Directory Logs  

microsoft.aadiam/tenants  

- [AADB2CRequestLogs](aadb2crequestlogs.md)

### Azure AD Domain Services  

Microsoft.AAD/domainServices  

- [AzureActivity](azureactivity.md)
- [AADDomainServicesDNSAuditsDynamicUpdates](aaddomainservicesdnsauditsdynamicupdates.md)
- [AADDomainServicesDNSAuditsGeneral](aaddomainservicesdnsauditsgeneral.md)
- [AzureMetrics](azuremetrics.md)
- [AADDomainServicesAccountLogon](aaddomainservicesaccountlogon.md)
- [AADDomainServicesAccountManagement](aaddomainservicesaccountmanagement.md)
- [AADDomainServicesDirectoryServiceAccess](aaddomainservicesdirectoryserviceaccess.md)
- [AADDomainServicesLogonLogoff](aaddomainserviceslogonlogoff.md)
- [AADDomainServicesPolicyChange](aaddomainservicespolicychange.md)
- [AADDomainServicesPrivilegeUse](aaddomainservicesprivilegeuse.md)

### Azure API for FHIR  

Microsoft.HealthcareApis/services  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [MicrosoftHealthcareApisAuditLogs](microsofthealthcareapisauditlogs.md)

### Azure Arc Enabled Kubernetes  

Microsoft.Kubernetes/connectedClusters  

- [AzureActivity](azureactivity.md)
- [AzureDiagnostics](azurediagnostics.md)
- [AzureMetrics](azuremetrics.md)
- [ContainerImageInventory](containerimageinventory.md)
- [ContainerInventory](containerinventory.md)
- [ContainerLog](containerlog.md)
- [ContainerLogV2](containerlogv2.md)
- [ContainerNodeInventory](containernodeinventory.md)
- [ContainerServiceLog](containerservicelog.md)
- [Heartbeat](heartbeat.md)
- [InsightsMetrics](insightsmetrics.md)
- [KubeEvents](kubeevents.md)
- [KubeMonAgentEvents](kubemonagentevents.md)
- [KubeNodeInventory](kubenodeinventory.md)
- [KubePodInventory](kubepodinventory.md)
- [KubePVInventory](kubepvinventory.md)
- [KubeServices](kubeservices.md)
- [Perf](perf.md)
- [Syslog](syslog.md)
- [ArcK8sAudit](arck8saudit.md)
- [ArcK8sAuditAdmin](arck8sauditadmin.md)
- [ArcK8sControlPlane](arck8scontrolplane.md)

### Azure Arc Provisioned Clusters  

Microsoft.HybridContainerservice/Provisionedclusters  

- [AzureActivity](azureactivity.md)
- [AzureDiagnostics](azurediagnostics.md)
- [AzureMetrics](azuremetrics.md)
- [ContainerImageInventory](containerimageinventory.md)
- [ContainerInventory](containerinventory.md)
- [ContainerLog](containerlog.md)
- [ContainerLogV2](containerlogv2.md)
- [ContainerNodeInventory](containernodeinventory.md)
- [ContainerServiceLog](containerservicelog.md)
- [KubeEvents](kubeevents.md)
- [KubeNodeInventory](kubenodeinventory.md)
- [KubePodInventory](kubepodinventory.md)
- [KubePVInventory](kubepvinventory.md)
- [KubeServices](kubeservices.md)
- [KubeMonAgentEvents](kubemonagentevents.md)
- [InsightsMetrics](insightsmetrics.md)
- [Perf](perf.md)
- [Syslog](syslog.md)
- [Heartbeat](heartbeat.md)

### Azure Attestation  

Microsoft.Attestation/attestationProviders  

- [AzureActivity](azureactivity.md)
- [AzureAttestationDiagnostics](azureattestationdiagnostics.md)

### Azure Autonomous Development Platform workspace  

Microsoft.AutonomousDevelopmentPlatform/workspaces  

- [AzureActivity](azureactivity.md)
- [ADPRequests](adprequests.md)
- [ADPAudit](adpaudit.md)
- [ADPDiagnostics](adpdiagnostics.md)

### Azure Blockchain Service  

Microsoft.Blockchain/blockchainMembers  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [BlockchainApplicationLog](blockchainapplicationlog.md)
- [BlockchainProxyLog](blockchainproxylog.md)

### Azure Cache for Redis  

microsoft.cache/redis  

- [ACRConnectedClientList](acrconnectedclientlist.md)
- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)

### Azure Cache for Redis Enterprise  

Microsoft.Cache/redisEnterprise  

- [REDConnectionEvents](redconnectionevents.md)

### Azure CloudHsm  

Microsoft.HardwareSecurityModules/cloudHsmClusters  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [CHSMManagementAuditLogs](chsmmanagementauditlogs.md)

### Azure Cosmos DB  

Microsoft.DocumentDb/databaseAccounts  

- [AzureActivity](azureactivity.md)
- [CDBDataPlaneRequests](cdbdataplanerequests.md)
- [CDBPartitionKeyStatistics](cdbpartitionkeystatistics.md)
- [CDBPartitionKeyRUConsumption](cdbpartitionkeyruconsumption.md)
- [CDBQueryRuntimeStatistics](cdbqueryruntimestatistics.md)
- [CDBMongoRequests](cdbmongorequests.md)
- [CDBCassandraRequests](cdbcassandrarequests.md)
- [CDBGremlinRequests](cdbgremlinrequests.md)
- [CDBTableApiRequests](cdbtableapirequests.md)
- [CDBControlPlaneRequests](cdbcontrolplanerequests.md)
- [AzureMetrics](azuremetrics.md)
- [AzureDiagnostics](azurediagnostics.md)

### Azure Cosmos DB for MongoDB (vCore)  

Microsoft.DocumentDB/mongoClusters  

- [VCoreMongoRequests](vcoremongorequests.md)

### Azure Cosmos DB for PostgreSQL  

Microsoft.DBForPostgreSQL/servergroupsv2  

- [AzureActivity](azureactivity.md)
- [AzureDiagnostics](azurediagnostics.md)
- [AzureMetrics](azuremetrics.md)

### Azure Data Explorer Clusters  

Microsoft.Kusto/Clusters  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [FailedIngestion](failedingestion.md)
- [SucceededIngestion](succeededingestion.md)
- [ADXIngestionBatching](adxingestionbatching.md)
- [ADXCommand](adxcommand.md)
- [ADXQuery](adxquery.md)
- [ADXTableUsageStatistics](adxtableusagestatistics.md)
- [ADXTableDetails](adxtabledetails.md)
- [ADXJournal](adxjournal.md)

### Azure Data Manager for Energy  

Microsoft.OpenEnergyPlatform/energyServices  

- [OEPAirFlowTask](oepairflowtask.md)
- [OEPElasticOperator](oepelasticoperator.md)
- [OEPElasticsearch](oepelasticsearch.md)
- [OEPAuditLogs](oepauditlogs.md)
- [OEPDataplaneLogs](oepdataplanelogs.md)

### Azure Data Transfer  

Microsoft.AzureDataTransfer/connections  

- [DataTransferOperations](datatransferoperations.md)

### Azure Database for MariaDB Servers  

Microsoft.DBforMariaDB/servers  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AzureDiagnostics](azurediagnostics.md)

### Azure Database for MySQL Flexible Servers  

Microsoft.DBForMySQL/flexibleServers  

- [AzureActivity](azureactivity.md)
- [AzureDiagnostics](azurediagnostics.md)
- [AzureMetrics](azuremetrics.md)

### Azure Database for MySQL Servers  

Microsoft.DBforMySQL/servers  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AzureDiagnostics](azurediagnostics.md)

### Azure Database for PostgreSQL Flexible Servers  

Microsoft.DBForPostgreSQL/flexibleServers  

- [AzureActivity](azureactivity.md)
- [AzureDiagnostics](azurediagnostics.md)
- [AzureMetrics](azuremetrics.md)

### Azure Database for PostgreSQL Servers  

Microsoft.DBforPostgreSQL/servers  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AzureDiagnostics](azurediagnostics.md)

### Azure Database for PostgreSQL Servers V2  

Microsoft.DBforPostgreSQL/serversv2  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AzureDiagnostics](azurediagnostics.md)

### Azure Databricks Services  

Microsoft.Databricks/workspaces  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [DatabricksBrickStoreHttpGateway](databricksbrickstorehttpgateway.md)
- [DatabricksDashboards](databricksdashboards.md)
- [DatabricksCloudStorageMetadata](databrickscloudstoragemetadata.md)
- [DatabricksPredictiveOptimization](databrickspredictiveoptimization.md)
- [DatabricksDataMonitoring](databricksdatamonitoring.md)
- [DatabricksIngestion](databricksingestion.md)
- [DatabricksMarketplaceConsumer](databricksmarketplaceconsumer.md)
- [DatabricksLineageTracking](databrickslineagetracking.md)
- [DatabricksFilesystem](databricksfilesystem.md)
- [DatabricksAccounts](databricksaccounts.md)
- [DatabricksClusters](databricksclusters.md)
- [DatabricksDBFS](databricksdbfs.md)
- [DatabricksInstancePools](databricksinstancepools.md)
- [DatabricksJobs](databricksjobs.md)
- [DatabricksNotebook](databricksnotebook.md)
- [DatabricksSQL](databrickssql.md)
- [DatabricksSQLPermissions](databrickssqlpermissions.md)
- [DatabricksSSH](databricksssh.md)
- [DatabricksSecrets](databrickssecrets.md)
- [DatabricksWorkspace](databricksworkspace.md)
- [DatabricksFeatureStore](databricksfeaturestore.md)
- [DatabricksGenie](databricksgenie.md)
- [DatabricksGlobalInitScripts](databricksglobalinitscripts.md)
- [DatabricksIAMRole](databricksiamrole.md)
- [DatabricksMLflowAcledArtifact](databricksmlflowacledartifact.md)
- [DatabricksMLflowExperiment](databricksmlflowexperiment.md)
- [DatabricksRemoteHistoryService](databricksremotehistoryservice.md)
- [DatabricksGitCredentials](databricksgitcredentials.md)
- [DatabricksWebTerminal](databrickswebterminal.md)
- [DatabricksDatabricksSQL](databricksdatabrickssql.md)

### Azure Digital Twins  

Microsoft.DigitalTwins/digitalTwinsInstances  

- [AzureActivity](azureactivity.md)
- [ADTDataHistoryOperation](adtdatahistoryoperation.md)
- [ADTDigitalTwinsOperation](adtdigitaltwinsoperation.md)
- [ADTEventRoutesOperation](adteventroutesoperation.md)
- [ADTModelsOperation](adtmodelsoperation.md)
- [ADTQueryOperation](adtqueryoperation.md)

### Azure HPC Cache  

Microsoft.StorageCache/caches  

- [StorageCacheOperationEvents](storagecacheoperationevents.md)
- [StorageCacheUpgradeEvents](storagecacheupgradeevents.md)
- [StorageCacheWarningEvents](storagecachewarningevents.md)

### Azure Load Testing  

Microsoft.LoadTestService/loadtests  

- [AzureActivity](azureactivity.md)
- [AzureLoadTestingOperation](azureloadtestingoperation.md)

### Azure Managed CCF  

Microsoft.ConfidentialLedger/ManagedCCFs  

- [CCFApplicationLogs](ccfapplicationlogs.md)

### Azure Managed HSM  

Microsoft.KeyVault/managedHSMs  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AZKVAuditLogs](azkvauditlogs.md)

### Azure Managed Instance for Apache Cassandra  

Microsoft.DocumentDB/cassandraClusters  

- [AzureActivity](azureactivity.md)
- [CassandraAudit](cassandraaudit.md)
- [CassandraLogs](cassandralogs.md)

### Azure Managed Lustre  

Microsoft.StorageCache/amlFilesytems  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AFSAuditLogs](afsauditlogs.md)

### Azure Managed Workspace for Grafana  

Microsoft.Dashboard/grafana  

- [AzureActivity](azureactivity.md)
- [AGSGrafanaLoginEvents](agsgrafanaloginevents.md)

### Azure Monitor autoscale settings  

Microsoft.Insights/AutoscaleSettings  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AutoscaleEvaluationsLog](autoscaleevaluationslog.md)
- [AutoscaleScaleActionsLog](autoscalescaleactionslog.md)

### Azure Monitor Workspace  

Microsoft.Monitor/accounts  

- [AMWMetricsUsageDetails](amwmetricsusagedetails.md)

### Azure Operator Insights - Data Product  

Microsoft.NetworkAnalytics/DataProducts  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AOIDigestion](aoidigestion.md)
- [AOIDatabaseQuery](aoidatabasequery.md)
- [AOIStorage](aoistorage.md)

### Azure PlayFab  

Microsoft.PlayFab/titles  

- [PFTitleAuditLogs](pftitleauditlogs.md)

### Azure Sphere  

Microsoft.AzureSphere/catalogs  

- [ASCAuditLogs](ascauditlogs.md)
- [ASCDeviceEvents](ascdeviceevents.md)

### Azure Spring Apps  

Microsoft.AppPlatform/Spring  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AppPlatformLogsforSpring](appplatformlogsforspring.md)
- [AppPlatformSystemLogs](appplatformsystemlogs.md)
- [AppPlatformIngressLogs](appplatformingresslogs.md)
- [AppPlatformBuildLogs](appplatformbuildlogs.md)
- [AppPlatformContainerEventLogs](appplatformcontainereventlogs.md)

### Azure Stack HCI  

Microsoft.AzureStackHCI/VirtualMachines  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [ADAssessmentRecommendation](adassessmentrecommendation.md)
- [ADReplicationResult](adreplicationresult.md)
- [ComputerGroup](computergroup.md)
- [ContainerLog](containerlog.md)
- [DnsEvents](dnsevents.md)
- [DnsInventory](dnsinventory.md)
- [SecurityBaselineSummary](securitybaselinesummary.md)
- [SQLAssessmentRecommendation](sqlassessmentrecommendation.md)
- [ConfigurationChange](configurationchange.md)
- [ConfigurationData](configurationdata.md)
- [Event](event.md)
- [Heartbeat](heartbeat.md)
- [Perf](perf.md)
- [ProtectionStatus](protectionstatus.md)
- [SecurityBaseline](securitybaseline.md)
- [SecurityEvent](securityevent.md)
- [Syslog](syslog.md)
- [Update](update.md)
- [UpdateRunProgress](updaterunprogress.md)
- [UpdateSummary](updatesummary.md)
- [VMBoundPort](vmboundport.md)
- [VMConnection](vmconnection.md)
- [VMComputer](vmcomputer.md)
- [VMProcess](vmprocess.md)
- [W3CIISLog](w3ciislog.md)
- [WindowsFirewall](windowsfirewall.md)
- [WireData](wiredata.md)
- [InsightsMetrics](insightsmetrics.md)
- [HealthStateChangeEvent](healthstatechangeevent.md)
- [CommonSecurityLog](commonsecuritylog.md)

### Azure Stack HCI  

Microsoft.AzureStackHCI/clusters  

- [Perf](perf.md)
- [Event](event.md)

### Azure Storage Mover  

Microsoft.StorageMover/storageMovers  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [StorageMoverCopyLogsFailed](storagemovercopylogsfailed.md)
- [StorageMoverCopyLogsTransferred](storagemovercopylogstransferred.md)
- [StorageMoverJobRunLogs](storagemoverjobrunlogs.md)

### Azure Traffic Collector  

Microsoft.NetworkFunction/AzureTrafficCollectors  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [ATCExpressRouteCircuitIpfix](atcexpressroutecircuitipfix.md)
- [ATCPrivatePeeringMetadata](atcprivatepeeringmetadata.md)

### Azure Virtual Network Manager  

Microsoft.Network/networkManagers  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AVNMNetworkGroupMembershipChange](avnmnetworkgroupmembershipchange.md)
- [AVNMRuleCollectionChange](avnmrulecollectionchange.md)
- [AVNMConnectivityConfigurationChange](avnmconnectivityconfigurationchange.md)
- [AVNMIPAMPoolAllocationChange](avnmipampoolallocationchange.md)

### Bastions  

Microsoft.Network/bastionHosts  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [MicrosoftAzureBastionAuditLogs](microsoftazurebastionauditlogs.md)

### Batch Accounts  

microsoft.batch/batchaccounts  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AzureDiagnostics](azurediagnostics.md)

### Bot Services  

Microsoft.BotService/botServices  

- [AzureActivity](azureactivity.md)
- [ABSBotRequests](absbotrequests.md)

### CDN Profiles  

Microsoft.Cdn/profiles  

- [AzureActivity](azureactivity.md)
- [AzureDiagnostics](azurediagnostics.md)

### Chaos Experiment  

Microsoft.Chaos/experiments  

- [AzureActivity](azureactivity.md)
- [ChaosStudioExperimentEventLogs](chaosstudioexperimenteventlogs.md)

### Cognitive Services  

microsoft.cognitiveservices/accounts  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AzureDiagnostics](azurediagnostics.md)

### Communication Services  

Microsoft.Communication/CommunicationServices  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [ACSChatIncomingOperations](acschatincomingoperations.md)
- [ACSSMSIncomingOperations](acssmsincomingoperations.md)
- [ACSAuthIncomingOperations](acsauthincomingoperations.md)
- [ACSBillingUsage](acsbillingusage.md)
- [ACSCallDiagnostics](acscalldiagnostics.md)
- [ACSCallSurvey](acscallsurvey.md)
- [ACSCallClientOperations](acscallclientoperations.md)
- [ACSCallClientMediaStatsTimeSeries](acscallclientmediastatstimeseries.md)
- [ACSCallSummary](acscallsummary.md)
- [ACSEmailSendMailOperational](acsemailsendmailoperational.md)
- [ACSEmailStatusUpdateOperational](acsemailstatusupdateoperational.md)
- [ACSEmailUserEngagementOperational](acsemailuserengagementoperational.md)
- [ACSCallRecordingIncomingOperations](acscallrecordingincomingoperations.md)
- [ACSCallRecordingSummary](acscallrecordingsummary.md)
- [ACSCallClosedCaptionsSummary](acscallclosedcaptionssummary.md)
- [ACSJobRouterIncomingOperations](acsjobrouterincomingoperations.md)
- [ACSRoomsIncomingOperations](acsroomsincomingoperations.md)
- [ACSCallAutomationIncomingOperations](acscallautomationincomingoperations.md)
- [ACSCallAutomationMediaSummary](acscallautomationmediasummary.md)
- [ACSAdvancedMessagingOperations](acsadvancedmessagingoperations.md)

### Container Apps  

Microsoft.App/managedEnvironments  

- [AzureActivity](azureactivity.md)
- [ContainerAppConsoleLogs](containerappconsolelogs.md)
- [ContainerAppSystemLogs](containerappsystemlogs.md)
- [AppEnvSpringAppConsoleLogs](appenvspringappconsolelogs.md)

### Container Registries  

Microsoft.ContainerRegistry/registries  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [ContainerRegistryLoginEvents](containerregistryloginevents.md)
- [ContainerRegistryRepositoryEvents](containerregistryrepositoryevents.md)

### Data Collection Rules  

Microsoft.Insights/datacollectionrules  

- [DCRLogErrors](dcrlogerrors.md)

### Data factories  

Microsoft.DataFactory/factories  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AzureDiagnostics](azurediagnostics.md)
- [ADFActivityRun](adfactivityrun.md)
- [ADFPipelineRun](adfpipelinerun.md)
- [ADFTriggerRun](adftriggerrun.md)
- [ADFSandboxActivityRun](adfsandboxactivityrun.md)
- [ADFSandboxPipelineRun](adfsandboxpipelinerun.md)
- [ADFSSISIntegrationRuntimeLogs](adfssisintegrationruntimelogs.md)
- [ADFSSISPackageEventMessageContext](adfssispackageeventmessagecontext.md)
- [ADFSSISPackageEventMessages](adfssispackageeventmessages.md)
- [ADFSSISPackageExecutableStatistics](adfssispackageexecutablestatistics.md)
- [ADFSSISPackageExecutionComponentPhases](adfssispackageexecutioncomponentphases.md)
- [ADFSSISPackageExecutionDataStatistics](adfssispackageexecutiondatastatistics.md)

### Data Lake Analytics  

Microsoft.DataLakeAnalytics/accounts  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AzureDiagnostics](azurediagnostics.md)

### Data Lake Storage Gen1  

Microsoft.DataLakeStore/accounts  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AzureDiagnostics](azurediagnostics.md)

### Data Share  

Microsoft.DataShare/accounts  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [MicrosoftDataShareSentSnapshotLog](microsoftdatasharesentsnapshotlog.md)
- [MicrosoftDataShareReceivedSnapshotLog](microsoftdatasharereceivedsnapshotlog.md)

### Defender for Storage Settings  

Microsoft.Security/DefenderForStorageSettings  

- [StorageMalwareScanningResults](storagemalwarescanningresults.md)

### Desktop Virtualization Application Groups  

Microsoft.DesktopVirtualization/applicationGroups  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [WVDErrors](wvderrors.md)
- [WVDCheckpoints](wvdcheckpoints.md)
- [WVDManagement](wvdmanagement.md)

### Desktop Virtualization Host Pools  

Microsoft.DesktopVirtualization/hostPools  

- [WVDAgentHealthStatus](wvdagenthealthstatus.md)
- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [WVDConnections](wvdconnections.md)
- [WVDErrors](wvderrors.md)
- [WVDCheckpoints](wvdcheckpoints.md)
- [WVDManagement](wvdmanagement.md)
- [WVDHostRegistrations](wvdhostregistrations.md)
- [WVDConnectionNetworkData](wvdconnectionnetworkdata.md)
- [WVDSessionHostManagement](wvdsessionhostmanagement.md)
- [WVDAutoscaleEvaluationPooled](wvdautoscaleevaluationpooled.md)
- [WVDConnectionGraphicsDataPreview](wvdconnectiongraphicsdatapreview.md)

### Desktop Virtualization workspaces  

Microsoft.DesktopVirtualization/workspaces  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [WVDFeeds](wvdfeeds.md)
- [WVDErrors](wvderrors.md)
- [WVDCheckpoints](wvdcheckpoints.md)
- [WVDManagement](wvdmanagement.md)

### Dev Centers  

Microsoft.DevCenter/devcenters  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [DevCenterDiagnosticLogs](devcenterdiagnosticlogs.md)
- [DevCenterResourceOperationLogs](devcenterresourceoperationlogs.md)
- [DevCenterBillingEventLogs](devcenterbillingeventlogs.md)

### Device Provisioning Services  

Microsoft.Devices/ProvisioningServices  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AzureDiagnostics](azurediagnostics.md)

### DNS Resolver Policies  

Microsoft.Network/dnsResolverPolicies  

- [AzureActivity](azureactivity.md)
- [DNSQueryLogs](dnsquerylogs.md)

### Dynamics 365 Customer Insights  

Microsoft.D365CustomerInsights/instances  

- [AzureActivity](azureactivity.md)
- [CIEventsAudit](cieventsaudit.md)
- [CIEventsOperational](cieventsoperational.md)

### Event Grid Domains  

Microsoft.EventGrid/domains  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AegDeliveryFailureLogs](aegdeliveryfailurelogs.md)
- [AegPublishFailureLogs](aegpublishfailurelogs.md)
- [AegDataPlaneRequests](aegdataplanerequests.md)

### Event Grid Namespaces  

Microsoft.EventGrid/namespaces  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [EGNSuccessfulMqttConnections](egnsuccessfulmqttconnections.md)
- [EGNFailedMqttConnections](egnfailedmqttconnections.md)
- [EGNMqttDisconnections](egnmqttdisconnections.md)
- [EGNFailedMqttPublishedMessages](egnfailedmqttpublishedmessages.md)
- [EGNFailedMqttSubscriptions](egnfailedmqttsubscriptions.md)
- [AzureDiagnostics](azurediagnostics.md)

### Event Grid Partner Namespaces  

Microsoft.EventGrid/partnerNamespaces  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AzureDiagnostics](azurediagnostics.md)
- [AegPublishFailureLogs](aegpublishfailurelogs.md)
- [AegDataPlaneRequests](aegdataplanerequests.md)

### Event Grid Partner Topics  

Microsoft.EventGrid/partnerTopics  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AzureDiagnostics](azurediagnostics.md)
- [AegDeliveryFailureLogs](aegdeliveryfailurelogs.md)

### Event Grid System Topics  

Microsoft.EventGrid/systemTopics  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AzureDiagnostics](azurediagnostics.md)
- [AegDeliveryFailureLogs](aegdeliveryfailurelogs.md)

### Event Grid Topics  

Microsoft.EventGrid/topics  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AegDataPlaneRequests](aegdataplanerequests.md)
- [AzureDiagnostics](azurediagnostics.md)
- [AegDeliveryFailureLogs](aegdeliveryfailurelogs.md)
- [AegPublishFailureLogs](aegpublishfailurelogs.md)

### Event Hubs  

Microsoft.EventHub/namespaces  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AzureDiagnostics](azurediagnostics.md)
- [AZMSApplicationMetricLogs](azmsapplicationmetriclogs.md)
- [AZMSOperationalLogs](azmsoperationallogs.md)
- [AZMSRunTimeAuditLogs](azmsruntimeauditlogs.md)
- [AZMSDiagnosticErrorLogs](azmsdiagnosticerrorlogs.md)
- [AZMSVnetConnectionEvents](azmsvnetconnectionevents.md)
- [AZMSArchiveLogs](azmsarchivelogs.md)
- [AZMSAutoscaleLogs](azmsautoscalelogs.md)
- [AZMSKafkaCoordinatorLogs](azmskafkacoordinatorlogs.md)
- [AZMSKafkaUserErrorLogs](azmskafkausererrorlogs.md)
- [AZMSCustomerManagedKeyUserLogs](azmscustomermanagedkeyuserlogs.md)

### Experiment Workspace  

Microsoft.Experimentation/experimentWorkspaces  

- [AzureActivity](azureactivity.md)
- [AEWAuditLogs](aewauditlogs.md)
- [AEWComputePipelinesLogs](aewcomputepipelineslogs.md)
- [AEWAssignmentBlobLogs](aewassignmentbloblogs.md)

### ExpressRoute Circuits  

Microsoft.Network/expressRouteCircuits  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AzureDiagnostics](azurediagnostics.md)

### Firewalls  

Microsoft.Network/azureFirewalls  

- [AZFWNetworkRule](azfwnetworkrule.md)
- [AZFWFatFlow](azfwfatflow.md)
- [AZFWFlowTrace](azfwflowtrace.md)
- [AZFWApplicationRule](azfwapplicationrule.md)
- [AZFWThreatIntel](azfwthreatintel.md)
- [AZFWNatRule](azfwnatrule.md)
- [AZFWIdpsSignature](azfwidpssignature.md)
- [AZFWDnsQuery](azfwdnsquery.md)
- [AZFWInternalFqdnResolutionFailure](azfwinternalfqdnresolutionfailure.md)
- [AZFWNetworkRuleAggregation](azfwnetworkruleaggregation.md)
- [AZFWApplicationRuleAggregation](azfwapplicationruleaggregation.md)
- [AZFWNatRuleAggregation](azfwnatruleaggregation.md)
- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AzureDiagnostics](azurediagnostics.md)

### Front Doors  

Microsoft.Network/frontdoors  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AzureDiagnostics](azurediagnostics.md)

### HDInsight Clusters  

Microsoft.HDInsight/Clusters  

- [AzureActivity](azureactivity.md)
- [HDInsightKafkaLogs](hdinsightkafkalogs.md)
- [HDInsightKafkaMetrics](hdinsightkafkametrics.md)
- [HDInsightHBaseLogs](hdinsighthbaselogs.md)
- [HDInsightHBaseMetrics](hdinsighthbasemetrics.md)
- [HDInsightStormLogs](hdinsightstormlogs.md)
- [HDInsightStormMetrics](hdinsightstormmetrics.md)
- [HDInsightStormTopologyMetrics](hdinsightstormtopologymetrics.md)
- [HDInsightGatewayAuditLogs](hdinsightgatewayauditlogs.md)
- [HDInsightAmbariSystemMetrics](hdinsightambarisystemmetrics.md)
- [HDInsightAmbariClusterAlerts](hdinsightambariclusteralerts.md)
- [HDInsightSparkApplicationEvents](hdinsightsparkapplicationevents.md)
- [HDInsightSparkBlockManagerEvents](hdinsightsparkblockmanagerevents.md)
- [HDInsightSparkEnvironmentEvents](hdinsightsparkenvironmentevents.md)
- [HDInsightJupyterNotebookEvents](hdinsightjupyternotebookevents.md)
- [HDInsightSparkExecutorEvents](hdinsightsparkexecutorevents.md)
- [HDInsightSparkExtraEvents](hdinsightsparkextraevents.md)
- [HDInsightSparkJobEvents](hdinsightsparkjobevents.md)
- [HDInsightSparkSQLExecutionEvents](hdinsightsparksqlexecutionevents.md)
- [HDInsightSparkStageEvents](hdinsightsparkstageevents.md)
- [HDInsightSparkStageTaskAccumulables](hdinsightsparkstagetaskaccumulables.md)
- [HDInsightSparkTaskEvents](hdinsightsparktaskevents.md)
- [HDInsightSparkLogs](hdinsightsparklogs.md)
- [HDInsightSecurityLogs](hdinsightsecuritylogs.md)
- [HDInsightRangerAuditLogs](hdinsightrangerauditlogs.md)
- [HDInsightHiveAndLLAPLogs](hdinsighthiveandllaplogs.md)
- [HDInsightHiveAndLLAPMetrics](hdinsighthiveandllapmetrics.md)
- [HDInsightHadoopAndYarnLogs](hdinsighthadoopandyarnlogs.md)
- [HDInsightHadoopAndYarnMetrics](hdinsighthadoopandyarnmetrics.md)
- [HDInsightOozieLogs](hdinsightoozielogs.md)
- [HDInsightHiveQueryAppStats](hdinsighthivequeryappstats.md)
- [HDInsightHiveTezAppStats](hdinsighthivetezappstats.md)

### Health Data Services  

Microsoft.HealthcareApis/workspaces  

- [AHDSMedTechDiagnosticLogs](ahdsmedtechdiagnosticlogs.md)
- [AHDSDicomDiagnosticLogs](ahdsdicomdiagnosticlogs.md)
- [AHDSDicomAuditLogs](ahdsdicomauditlogs.md)

### Integration Account.  

Microsoft.Logic/integrationAccounts  

- [AzureActivity](azureactivity.md)

### Intune Specialist Reports.  

microsoft.intune/operations  

- [Windows365AuditLogs](windows365auditlogs.md)

### IoT Hub  

Microsoft.Devices/IotHubs  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AzureDiagnostics](azurediagnostics.md)
- [IoTHubDistributedTracing](iothubdistributedtracing.md)
- [InsightsMetrics](insightsmetrics.md)

### Key Vaults  

Microsoft.KeyVault/vaults  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AZKVAuditLogs](azkvauditlogs.md)
- [AZKVPolicyEvaluationDetailsLogs](azkvpolicyevaluationdetailslogs.md)
- [AzureDiagnostics](azurediagnostics.md)

### Kubernetes Services  

Microsoft.ContainerService/managedClusters  

- [AzureActivity](azureactivity.md)
- [AzureDiagnostics](azurediagnostics.md)
- [AzureMetrics](azuremetrics.md)
- [ContainerImageInventory](containerimageinventory.md)
- [ContainerInventory](containerinventory.md)
- [ContainerLog](containerlog.md)
- [ContainerLogV2](containerlogv2.md)
- [ContainerNodeInventory](containernodeinventory.md)
- [ContainerServiceLog](containerservicelog.md)
- [Heartbeat](heartbeat.md)
- [InsightsMetrics](insightsmetrics.md)
- [KubeEvents](kubeevents.md)
- [KubeMonAgentEvents](kubemonagentevents.md)
- [KubeNodeInventory](kubenodeinventory.md)
- [KubePodInventory](kubepodinventory.md)
- [KubePVInventory](kubepvinventory.md)
- [KubeServices](kubeservices.md)
- [Perf](perf.md)
- [Syslog](syslog.md)
- [AKSAudit](aksaudit.md)
- [AKSAuditAdmin](aksauditadmin.md)
- [AKSControlPlane](akscontrolplane.md)

### Load Balancers  

Microsoft.Network/LoadBalancers  

- [ALBHealthEvent](albhealthevent.md)
- [AzureActivity](azureactivity.md)

### Log Analytics workspaces  

Microsoft.OperationalInsights/Workspaces  

- [LAQueryLogs](laquerylogs.md)
- [LASummaryLogs](lasummarylogs.md)

### Logic Apps  

Microsoft.Logic/workflows  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AzureDiagnostics](azurediagnostics.md)
- [LogicAppWorkflowRuntime](logicappworkflowruntime.md)

### Machine Learning  

Microsoft.MachineLearningServices/workspaces  

- [AzureActivity](azureactivity.md)
- [AmlOnlineEndpointConsoleLog](amlonlineendpointconsolelog.md)
- [AmlOnlineEndpointTrafficLog](amlonlineendpointtrafficlog.md)
- [AmlOnlineEndpointEventLog](amlonlineendpointeventlog.md)
- [AzureMetrics](azuremetrics.md)
- [AmlComputeClusterEvent](amlcomputeclusterevent.md)
- [AmlComputeClusterNodeEvent](amlcomputeclusternodeevent.md)
- [AmlComputeJobEvent](amlcomputejobevent.md)
- [AmlRunStatusChangedEvent](amlrunstatuschangedevent.md)
- [AmlComputeCpuGpuUtilization](amlcomputecpugpuutilization.md)
- [AmlComputeInstanceEvent](amlcomputeinstanceevent.md)
- [AmlDataLabelEvent](amldatalabelevent.md)
- [AmlDataSetEvent](amldatasetevent.md)
- [AmlDataStoreEvent](amldatastoreevent.md)
- [AmlDeploymentEvent](amldeploymentevent.md)
- [AmlEnvironmentEvent](amlenvironmentevent.md)
- [AmlInferencingEvent](amlinferencingevent.md)
- [AmlModelsEvent](amlmodelsevent.md)
- [AmlPipelineEvent](amlpipelineevent.md)
- [AmlRunEvent](amlrunevent.md)

### Machine Learning  

Microsoft.MachineLearningServices/registries  

- [AzureActivity](azureactivity.md)
- [AmlRegistryReadEventsLog](amlregistryreadeventslog.md)
- [AmlRegistryWriteEventsLog](amlregistrywriteeventslog.md)

### Media Services  

Microsoft.Media/mediaservices  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AMSKeyDeliveryRequests](amskeydeliveryrequests.md)
- [AMSMediaAccountHealth](amsmediaaccounthealth.md)
- [AMSLiveEventOperations](amsliveeventoperations.md)
- [AMSStreamingEndpointRequests](amsstreamingendpointrequests.md)
- [AzureDiagnostics](azurediagnostics.md)

### Microsoft App Configuration  

Microsoft.AppConfiguration/configurationStores  

- [AzureActivity](azureactivity.md)
- [AACHttpRequest](aachttprequest.md)
- [AACAudit](aacaudit.md)

### Microsoft Connected Cache  

Microsoft.ConnectedCache/CacheNodes  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [MCCEventLogs](mcceventlogs.md)

### Microsoft Connected Vehicle Platform  

Microsoft.ConnectedVehicle/platformAccounts  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [MCVPOperationLogs](mcvpoperationlogs.md)
- [MCVPAuditLogs](mcvpauditlogs.md)

### Microsoft Container Instances Services  

Microsoft.ContainerInstance/containerGroups  

- [ContainerInstanceLog](containerinstancelog.md)
- [ContainerEvent](containerevent.md)

### Microsoft Defender for Cloud  

Microsoft.Security/Security  

- [SecurityAttackPathData](securityattackpathdata.md)

### Microsoft Graph Logs  

Microsoft.Graph/tenants  

- [AzureActivity](azureactivity.md)
- [SigninLogs](signinlogs.md)
- [AuditLogs](auditlogs.md)

### Microsoft Playwright Testing  

Microsoft.AzurePlaywrightService/accounts  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)

### Microsoft.AgFoodPlatform/farmBeats  

Microsoft.AgFoodPlatform/farmBeats  

- [AgriFoodFarmManagementLogs](agrifoodfarmmanagementlogs.md)
- [AgriFoodWeatherLogs](agrifoodweatherlogs.md)
- [AgriFoodSatelliteLogs](agrifoodsatellitelogs.md)
- [AgriFoodFarmOperationLogs](agrifoodfarmoperationlogs.md)
- [AgriFoodProviderAuthLogs](agrifoodproviderauthlogs.md)
- [AgriFoodApplicationAuditLogs](agrifoodapplicationauditlogs.md)
- [AgriFoodModelInferenceLogs](agrifoodmodelinferencelogs.md)
- [AgriFoodInsightLogs](agrifoodinsightlogs.md)
- [AgriFoodJobProcessedLogs](agrifoodjobprocessedlogs.md)
- [AgriFoodSensorManagementLogs](agrifoodsensormanagementlogs.md)

### Microsoft.OpenLogisticsPlatform/Workspaces  

Microsoft.OpenLogisticsPlatform/Workspaces  

- [OLPSupplyChainEvents](olpsupplychainevents.md)
- [OLPSupplyChainEntityOperations](olpsupplychainentityoperations.md)

### Microsoft.Purview/accounts  

Microsoft.Purview/accounts  

- [AzureActivity](azureactivity.md)
- [PurviewScanStatusLogs](purviewscanstatuslogs.md)
- [PurviewDataSensitivityLogs](purviewdatasensitivitylogs.md)
- [PurviewSecurityLogs](purviewsecuritylogs.md)

### Network Devices (Operator Nexus)  

Microsoft.ManagedNetworkFabric/networkDevices  

- [Azuremetrics](azuremetrics.md)
- [AzureActivity](azureactivity.md)
- [MNFDeviceUpdates](mnfdeviceupdates.md)
- [MNFSystemStateMessageUpdates](mnfsystemstatemessageupdates.md)
- [MNFSystemSessionHistoryUpdates](mnfsystemsessionhistoryupdates.md)

### Network Interfaces  

Microsoft.Network/networkinterfaces  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AzureDiagnostics](azurediagnostics.md)

### Network Security Groups  

Microsoft.Network/NetworkSecurityGroups  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AzureDiagnostics](azurediagnostics.md)

### Network Security Perimeters  

Microsoft.Network/NetworkSecurityPerimeters  

- [NSPAccessLogs](nspaccesslogs.md)

### Network Watcher - Connection Monitor  

Microsoft.Network/NetworkWatchers/Connectionmonitors  

- [AzureActivity](azureactivity.md)
- [NWConnectionMonitorTestResult](nwconnectionmonitortestresult.md)
- [NWConnectionMonitorPathResult](nwconnectionmonitorpathresult.md)
- [NWConnectionMonitorDNSResult](nwconnectionmonitordnsresult.md)

### Nexus BareMetal Machines  

Microsoft.NetworkCloud/bareMetalMachines  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [NCBMSystemLogs](ncbmsystemlogs.md)
- [NCBMSecurityLogs](ncbmsecuritylogs.md)
- [NCBMSecurityDefenderLogs](ncbmsecuritydefenderlogs.md)
- [NCBMBreakGlassAuditLogs](ncbmbreakglassauditlogs.md)

### Nexus Cluster Managers  

Microsoft.NetworkCloud/clusterManagers  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [NCMClusterOperationsLogs](ncmclusteroperationslogs.md)

### Nexus Clusters  

Microsoft.NetworkCloud/clusters  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [NCCKubernetesLogs](ncckuberneteslogs.md)
- [NCCVMOrchestrationLogs](nccvmorchestrationlogs.md)

### Nexus Storage Appliances  

Microsoft.NetworkCloud/storageAppliances  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [NCSStorageAudits](ncsstorageaudits.md)
- [NCSStorageAlerts](ncsstoragealerts.md)
- [NCSStorageLogs](ncsstoragelogs.md)

### NGINXaaS  

NGINX.NGINXPLUS/nginxDeployments  

- [NGXOperationLogs](ngxoperationlogs.md)
- [NGXSecurityLogs](ngxsecuritylogs.md)

### Power BI Datasets  

Microsoft.PowerBI/tenants  

- [PowerBIDatasetsTenant](powerbidatasetstenant.md)

### Power BI Datasets  

Microsoft.PowerBI/tenants/workspaces  

- [PowerBIDatasetsWorkspace](powerbidatasetsworkspace.md)

### Power BI Embedded  

microsoft.powerbidedicated/capacities  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AzureDiagnostics](azurediagnostics.md)

### Project CI Workspace  

Microsoft.DataCollaboration/workspaces  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [ACICollaborationAudit](acicollaborationaudit.md)

### Public IP Addresses  

Microsoft.Network/PublicIpAddresses  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AzureDiagnostics](azurediagnostics.md)

### Recovery Services Vaults  

Microsoft.RecoveryServices/Vaults  

- [AzureActivity](azureactivity.md)
- [ASRJobs](asrjobs.md)
- [ASRReplicatedItems](asrreplicateditems.md)
- [AzureBackupOperations](azurebackupoperations.md)
- [AzureDiagnostics](azurediagnostics.md)
- [CoreAzureBackup](coreazurebackup.md)
- [AddonAzureBackupJobs](addonazurebackupjobs.md)
- [AddonAzureBackupAlerts](addonazurebackupalerts.md)
- [AddonAzureBackupPolicy](addonazurebackuppolicy.md)
- [AddonAzureBackupStorage](addonazurebackupstorage.md)
- [AddonAzureBackupProtectedInstance](addonazurebackupprotectedinstance.md)

### Relay  

Microsoft.Relay/namespaces  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AZMSVnetConnectionEvents](azmsvnetconnectionevents.md)
- [AZMSHybridConnectionsEvents](azmshybridconnectionsevents.md)

### Search Services  

Microsoft.Search/searchServices  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AzureDiagnostics](azurediagnostics.md)

### Service Bus  

Microsoft.ServiceBus/namespaces  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AzureDiagnostics](azurediagnostics.md)
- [AZMSOperationalLogs](azmsoperationallogs.md)
- [AZMSVnetConnectionEvents](azmsvnetconnectionevents.md)
- [AZMSRunTimeAuditLogs](azmsruntimeauditlogs.md)
- [AZMSApplicationMetricLogs](azmsapplicationmetriclogs.md)
- [AZMSDiagnosticErrorLogs](azmsdiagnosticerrorlogs.md)

### Service Fabric Clusters  

Microsoft.ServiceFabric/clusters  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)

### SignalR  

Microsoft.SignalRService/SignalR  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [SignalRServiceDiagnosticLogs](signalrservicediagnosticlogs.md)

### SignalR Service WebPubSub  

Microsoft.SignalRService/WebPubSub  

- [AzureActivity](azureactivity.md)
- [WebPubSubHttpRequest](webpubsubhttprequest.md)
- [WebPubSubMessaging](webpubsubmessaging.md)
- [WebPubSubConnectivity](webpubsubconnectivity.md)

### SQL Databases  

Microsoft.Sql/servers/databases  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AzureDiagnostics](azurediagnostics.md)

### SQL Managed Instances  

Microsoft.Sql/managedInstances  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AzureDiagnostics](azurediagnostics.md)

### SQL Servers  

microsoft.sql/servers  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AzureDiagnostics](azurediagnostics.md)

### Storage Accounts  

Microsoft.Storage/storageAccounts  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [StorageTableLogs](storagetablelogs.md)
- [StorageQueueLogs](storagequeuelogs.md)
- [StorageFileLogs](storagefilelogs.md)
- [StorageBlobLogs](storagebloblogs.md)

### Stream Analytics jobs  

microsoft.streamanalytics/streamingjobs  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AzureDiagnostics](azurediagnostics.md)

### Synapse Workspaces  

Microsoft.Synapse/workspaces  

- [AzureActivity](azureactivity.md)
- [SynapseRbacOperations](synapserbacoperations.md)
- [SynapseGatewayApiRequests](synapsegatewayapirequests.md)
- [SynapseSqlPoolExecRequests](synapsesqlpoolexecrequests.md)
- [SynapseSqlPoolRequestSteps](synapsesqlpoolrequeststeps.md)
- [SynapseSqlPoolDmsWorkers](synapsesqlpooldmsworkers.md)
- [SynapseSqlPoolWaits](synapsesqlpoolwaits.md)
- [SynapseSqlPoolSqlRequests](synapsesqlpoolsqlrequests.md)
- [SynapseIntegrationPipelineRuns](synapseintegrationpipelineruns.md)
- [SynapseLinkEvent](synapselinkevent.md)
- [SynapseIntegrationActivityRuns](synapseintegrationactivityruns.md)
- [SynapseIntegrationTriggerRuns](synapseintegrationtriggerruns.md)
- [SynapseBigDataPoolApplicationsEnded](synapsebigdatapoolapplicationsended.md)
- [SynapseBuiltinSqlPoolRequestsEnded](synapsebuiltinsqlpoolrequestsended.md)
- [SQLSecurityAuditEvents](sqlsecurityauditevents.md)
- [SynapseScopePoolScopeJobsEnded](synapsescopepoolscopejobsended.md)
- [SynapseScopePoolScopeJobsStateChange](synapsescopepoolscopejobsstatechange.md)
- [AzureMetrics](azuremetrics.md)
- [SynapseDXCommand](synapsedxcommand.md)
- [SynapseDXFailedIngestion](synapsedxfailedingestion.md)
- [SynapseDXIngestionBatching](synapsedxingestionbatching.md)
- [SynapseDXQuery](synapsedxquery.md)
- [SynapseDXSucceededIngestion](synapsedxsucceededingestion.md)
- [SynapseDXTableUsageStatistics](synapsedxtableusagestatistics.md)
- [SynapseDXTableDetails](synapsedxtabledetails.md)

### System Center Virtual Machine Manager  

Microsoft.SCVMM/VirtualMachines  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [ADAssessmentRecommendation](adassessmentrecommendation.md)
- [ADReplicationResult](adreplicationresult.md)
- [ComputerGroup](computergroup.md)
- [ContainerLog](containerlog.md)
- [DnsEvents](dnsevents.md)
- [DnsInventory](dnsinventory.md)
- [SecurityBaselineSummary](securitybaselinesummary.md)
- [SQLAssessmentRecommendation](sqlassessmentrecommendation.md)
- [ConfigurationChange](configurationchange.md)
- [ConfigurationData](configurationdata.md)
- [Event](event.md)
- [Heartbeat](heartbeat.md)
- [Perf](perf.md)
- [ProtectionStatus](protectionstatus.md)
- [SecurityBaseline](securitybaseline.md)
- [SecurityEvent](securityevent.md)
- [Syslog](syslog.md)
- [Update](update.md)
- [UpdateRunProgress](updaterunprogress.md)
- [UpdateSummary](updatesummary.md)
- [VMBoundPort](vmboundport.md)
- [VMConnection](vmconnection.md)
- [VMComputer](vmcomputer.md)
- [VMProcess](vmprocess.md)
- [W3CIISLog](w3ciislog.md)
- [WindowsFirewall](windowsfirewall.md)
- [WireData](wiredata.md)
- [InsightsMetrics](insightsmetrics.md)
- [HealthStateChangeEvent](healthstatechangeevent.md)
- [CommonSecurityLog](commonsecuritylog.md)

### Time Series Insights Environments  

Microsoft.TimeSeriesInsights/environments  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [TSIIngress](tsiingress.md)

### Traffic Manager Profiles  

Microsoft.Network/trafficmanagerprofiles  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AzureDiagnostics](azurediagnostics.md)

### Video Indexer  

Microsoft.VideoIndexer/accounts  

- [VIAudit](viaudit.md)
- [VIIndexing](viindexing.md)

### Virtual Machine Scale Sets  

Microsoft.Compute/virtualMachineScaleSets  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [ConfigurationChange](configurationchange.md)
- [ConfigurationData](configurationdata.md)
- [ContainerLog](containerlog.md)
- [Event](event.md)
- [Heartbeat](heartbeat.md)
- [Perf](perf.md)
- [ProtectionStatus](protectionstatus.md)
- [SecurityBaseline](securitybaseline.md)
- [SecurityEvent](securityevent.md)
- [Syslog](syslog.md)
- [Update](update.md)
- [UpdateRunProgress](updaterunprogress.md)
- [UpdateSummary](updatesummary.md)
- [VMBoundPort](vmboundport.md)
- [VMConnection](vmconnection.md)
- [VMComputer](vmcomputer.md)
- [VMProcess](vmprocess.md)
- [W3CIISLog](w3ciislog.md)
- [WindowsFirewall](windowsfirewall.md)
- [WireData](wiredata.md)
- [InsightsMetrics](insightsmetrics.md)
- [CommonSecurityLog](commonsecuritylog.md)

### Virtual machines  

Microsoft.Compute/VirtualMachines  

- [Heartbeat](heartbeat.md)
- [W3CIISLog](w3ciislog.md)
- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [ADAssessmentRecommendation](adassessmentrecommendation.md)
- [ADReplicationResult](adreplicationresult.md)
- [ComputerGroup](computergroup.md)
- [ContainerLog](containerlog.md)
- [DnsEvents](dnsevents.md)
- [DnsInventory](dnsinventory.md)
- [SecurityBaselineSummary](securitybaselinesummary.md)
- [SQLAssessmentRecommendation](sqlassessmentrecommendation.md)
- [ConfigurationChange](configurationchange.md)
- [ConfigurationData](configurationdata.md)
- [Event](event.md)
- [Perf](perf.md)
- [ProtectionStatus](protectionstatus.md)
- [SecurityBaseline](securitybaseline.md)
- [SecurityEvent](securityevent.md)
- [Syslog](syslog.md)
- [Update](update.md)
- [UpdateRunProgress](updaterunprogress.md)
- [UpdateSummary](updatesummary.md)
- [VMBoundPort](vmboundport.md)
- [VMConnection](vmconnection.md)
- [VMComputer](vmcomputer.md)
- [VMProcess](vmprocess.md)
- [WindowsFirewall](windowsfirewall.md)
- [WireData](wiredata.md)
- [InsightsMetrics](insightsmetrics.md)
- [HealthStateChangeEvent](healthstatechangeevent.md)
- [CommonSecurityLog](commonsecuritylog.md)

### Virtual Network Gateways  

Microsoft.Network/virtualNetworkGateways  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AzureDiagnostics](azurediagnostics.md)

### Virtual Networks  

Microsoft.Network/virtualNetworks  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AzureDiagnostics](azurediagnostics.md)

### Virtual Private Network Gateways  

Microsoft.Network/vpnGateways  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [AzureDiagnostics](azurediagnostics.md)

### VMware  

Microsoft.ConenctedVMwarevSphere/VirtualMachines  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)
- [ADAssessmentRecommendation](adassessmentrecommendation.md)
- [ADReplicationResult](adreplicationresult.md)
- [ComputerGroup](computergroup.md)
- [ContainerLog](containerlog.md)
- [DnsEvents](dnsevents.md)
- [DnsInventory](dnsinventory.md)
- [SecurityBaselineSummary](securitybaselinesummary.md)
- [SQLAssessmentRecommendation](sqlassessmentrecommendation.md)
- [ConfigurationChange](configurationchange.md)
- [ConfigurationData](configurationdata.md)
- [Event](event.md)
- [Heartbeat](heartbeat.md)
- [Perf](perf.md)
- [ProtectionStatus](protectionstatus.md)
- [SecurityBaseline](securitybaseline.md)
- [SecurityEvent](securityevent.md)
- [Syslog](syslog.md)
- [Update](update.md)
- [UpdateRunProgress](updaterunprogress.md)
- [UpdateSummary](updatesummary.md)
- [VMBoundPort](vmboundport.md)
- [VMConnection](vmconnection.md)
- [VMComputer](vmcomputer.md)
- [VMProcess](vmprocess.md)
- [W3CIISLog](w3ciislog.md)
- [WindowsFirewall](windowsfirewall.md)
- [WireData](wiredata.md)
- [InsightsMetrics](insightsmetrics.md)
- [HealthStateChangeEvent](healthstatechangeevent.md)
- [CommonSecurityLog](commonsecuritylog.md)

### Workload Monitor  

Microsoft.WorkloadMonitor/monitors  

- [AzureActivity](azureactivity.md)
- [AzureMetrics](azuremetrics.md)

### Workload Monitoring of Azure Monitor Insights  

Microsoft.Insights/WorkloadMonitoring  

- [InsightsMetrics](insightsmetrics.md)

## Next steps

- [Analyze logs from Azure storage with Log Analytics](/azure/azure-monitor/essentials/resource-logs#send-to-log-analytics-workspace)
- [Learn more about resource logs](/azure/azure-monitor/essentials/platform-logs-overview)
- [Change resource log diagnostic settings using the Azure Monitor REST API](/rest/api/monitor/diagnosticsettings)
