---
title: Azure Monitor supported metrics by resource type
description: List of metrics available for each resource type with Azure Monitor.
author: EdB-MSFT
services: azure-monitor
ms.topic: reference
ms.service: azure-monitor
ms.custom: ignite-2022
ms.date: 01/02/2024
ms.author: edbaynash
ms.reviewer: priyamishra
---

# Supported metrics with Azure Monitor

> [!NOTE]
> This list is largely auto-generated. Any modification made to this list via GitHub might be written over without warning. Contact the author of this article for details on how to make permanent updates.

Date list was last updated: 01/02/2024.

Azure Monitor provides several ways to interact with metrics, including charting them in the Azure portal, accessing them through the REST API, or querying them by using PowerShell or the Azure CLI (Command Line Interface).  

This article is a complete list of all platform (that is, automatically collected) metrics currently available with the consolidated metric pipeline in Azure Monitor. Metrics changed or added after the date at the top of this article might not yet appear in the list. To query for and access the list of metrics programmatically, use the [2018-01-01 api-version](/rest/api/monitor/metricdefinitions). Other metrics not in this list might be available in the portal or through legacy APIs.

The metrics are organized by resource provider and resource type. For a list of services and the resource providers and types that belong to them, see [Resource providers for Azure services](/azure/azure-resource-manager/management/azure-services-resource-providers).  

## Exporting platform metrics to other locations

You can export the platform metrics from the Azure monitor pipeline to other locations in one of two ways:

- Use the [metrics REST API](/rest/api/monitor/metrics/list).
- Use [diagnostic settings](/azure/azure-monitor/essentials/diagnostic-settings?tabs=portal) to route platform metrics to: 
    - Azure Storage.
    - Azure Monitor Logs (and thus Log Analytics).
    - Event hubs, which is how you get them to non-Microsoft systems. 

Using diagnostic settings is the easiest way to route the metrics, but there are some limitations: 

- **Exportability**. All metrics are exportable through the REST API, but some can't be exported through diagnostic settings because of intricacies in the Azure Monitor back end. The column "Exportable via Diagnostic Settings" in the following tables lists which metrics can be exported in this way.  

- **Multi-dimensional metrics**. Sending multi-dimensional metrics to other locations via diagnostic settings is not currently supported. Metrics with dimensions are exported as flattened single-dimensional metrics, aggregated across dimension values. 

  For example, the *Incoming Messages* metric on an event hub can be explored and charted on a per-queue level. But when the metric is exported via diagnostic settings, it will be represented as all incoming messages across all queues in the event hub.

## Guest OS and host OS metrics

Metrics for the guest operating system (guest OS) that runs in Azure Virtual Machines, Service Fabric, and Cloud Services are *not* listed here. Guest OS metrics must be collected through one or more agents that run on or as part of the guest operating system. Guest OS metrics include performance counters that track guest CPU percentage or memory usage, both of which are frequently used for autoscaling or alerting. 

Host OS metrics *are* available and listed in the tables. Host OS metrics relate to the Hyper-V session that's hosting your guest OS session. 

> [!TIP]
> A best practice is to use and configure the Azure Monitor agent to send guest OS performance metrics into the same Azure Monitor metric database where platform metrics are stored. The agent routes guest OS metrics through the [custom metrics](/azure/azure-monitor/essentials/metrics-custom-overview) API. You can then chart, alert, and otherwise use guest OS metrics like platform metrics. 
>
> Alternatively or in addition, you can send the guest OS metrics to Azure Monitor Logs by using the same agent. There you can query on those metrics in combination with non-metric data by using Log Analytics. Standard [Log Analytics workspace costs](https://azure.microsoft.com/pricing/details/monitor/) would then apply.  

The Azure Monitor agent replaces the Azure Diagnostics extension and Log Analytics agent, which were previously used for guest OS routing. For important additional information, see [Overview of Azure Monitor agents](/azure/azure-monitor/agents/agents-overview).

## Table formatting

This latest update adds a new column and reorders the metrics to be alphabetical. The additional information means that the tables might have a horizontal scroll bar at the bottom, depending on the width of your browser window. If you seem to be missing information, use the scroll bar to see the entirety of the table.  
  
## Metrics by resource provider
  
  
    
  
### Microsoft.AAD<a name="microsoftaaddomainservices"></a>
  
  * [Microsoft.AAD/DomainServices](Microsoft-AAD-DomainServices-metrics.md)

  
### Microsoft.AnalysisServices<a name="microsoftanalysisservicesservers"></a>
  
  * [Microsoft.AnalysisServices/servers](Microsoft-AnalysisServices-servers-metrics.md)

  
### Microsoft.ApiManagement<a name="microsoftapimanagementservice"></a>
  
  * [Microsoft.ApiManagement/service](Microsoft-ApiManagement-service-metrics.md)

  
### Microsoft.App<a name="microsoftappcontainerapps"></a><a name="microsoftappmanagedenvironments"></a>
  
  * [Microsoft.App/containerapps](Microsoft-App-containerapps-metrics.md)
* [Microsoft.App/managedEnvironments](Microsoft-App-managedEnvironments-metrics.md)

  
### Microsoft.AppConfiguration<a name="microsoftappconfigurationconfigurationstores"></a>
  
  * [Microsoft.AppConfiguration/configurationStores](Microsoft-AppConfiguration-configurationStores-metrics.md)

  
### Microsoft.AppPlatform<a name="microsoftappplatformspring"></a>
  
  * [Microsoft.AppPlatform/Spring](Microsoft-AppPlatform-Spring-metrics.md)

  
### Microsoft.Automation<a name="microsoftautomationautomationaccounts"></a>
  
  * [Microsoft.Automation/automationAccounts](Microsoft-Automation-automationAccounts-metrics.md)

  
### microsoft.avs<a name="microsoftavsprivateclouds"></a>
  
  * [microsoft.avs/privateClouds](microsoft-avs-privateClouds-metrics.md)

  
### microsoft.azuresphere<a name="microsoftazurespherecatalogs"></a>
  
  * [microsoft.azuresphere/catalogs](microsoft-azuresphere-catalogs-metrics.md)

  
### Microsoft.azurestackhci<a name="microsoftazurestackhciclusters"></a>
  
  * [Microsoft.azurestackhci/clusters](Microsoft-azurestackhci-clusters-metrics.md)

  
### Microsoft.Batch<a name="microsoftbatchbatchaccounts"></a>
  
  * [Microsoft.Batch/batchaccounts](Microsoft-Batch-batchaccounts-metrics.md)

  
### microsoft.bing<a name="microsoftbingaccounts"></a>
  
  * [microsoft.bing/accounts](microsoft-bing-accounts-metrics.md)

  
### microsoft.botservice<a name="microsoftbotservicebotservices"></a>
  
  * [microsoft.botservice/botservices](microsoft-botservice-botservices-metrics.md)

  
### Microsoft.BotService<a name="microsoftbotservicebotserviceschannels"></a><a name="microsoftbotservicebotservicesconnections"></a><a name="microsoftbotservicechecknameavailability"></a><a name="microsoftbotservicehostsettings"></a><a name="microsoftbotservicelistauthserviceproviders"></a><a name="microsoftbotservicelistqnamakerendpointkeys"></a>
  
  * [Microsoft.BotService/botServices/channels](Microsoft-BotService-botServices-channels-metrics.md)
* [Microsoft.BotService/botServices/connections](Microsoft-BotService-botServices-connections-metrics.md)
* [Microsoft.BotService/checknameavailability](Microsoft-BotService-checknameavailability-metrics.md)
* [Microsoft.BotService/hostsettings](Microsoft-BotService-hostsettings-metrics.md)
* [Microsoft.BotService/listauthserviceproviders](Microsoft-BotService-listauthserviceproviders-metrics.md)
* [Microsoft.BotService/listqnamakerendpointkeys](Microsoft-BotService-listqnamakerendpointkeys-metrics.md)

  
### Microsoft.Cache<a name="microsoftcacheredis"></a><a name="microsoftcacheredisenterprise"></a>
  
  * [Microsoft.Cache/redis](Microsoft-Cache-redis-metrics.md)
* [Microsoft.Cache/redisEnterprise](Microsoft-Cache-redisEnterprise-metrics.md)

  
### Microsoft.Cdn<a name="microsoftcdncdnwebapplicationfirewallpolicies"></a><a name="microsoftcdnprofiles"></a>
  
  * [Microsoft.Cdn/cdnwebapplicationfirewallpolicies](Microsoft-Cdn-cdnwebapplicationfirewallpolicies-metrics.md)
* [Microsoft.Cdn/profiles](Microsoft-Cdn-profiles-metrics.md)

  
### Microsoft.ClassicCompute<a name="microsoftclassiccomputedomainnamesslotsroles"></a><a name="microsoftclassiccomputevirtualmachines"></a>
  
  * [Microsoft.ClassicCompute/domainNames/slots/roles](Microsoft-ClassicCompute-domainNames-slots-roles-metrics.md)
* [Microsoft.ClassicCompute/virtualMachines](Microsoft-ClassicCompute-virtualMachines-metrics.md)

  
### Microsoft.ClassicStorage<a name="microsoftclassicstoragestorageaccounts"></a><a name="microsoftclassicstoragestorageaccountsblobservices"></a><a name="microsoftclassicstoragestorageaccountsfileservices"></a><a name="microsoftclassicstoragestorageaccountsqueueservices"></a><a name="microsoftclassicstoragestorageaccountstableservices"></a>
  
  * [Microsoft.ClassicStorage/storageAccounts](Microsoft-ClassicStorage-storageAccounts-metrics.md)
* [Microsoft.ClassicStorage/storageAccounts/blobServices](Microsoft-ClassicStorage-storageAccounts-blobServices-metrics.md)
* [Microsoft.ClassicStorage/storageAccounts/fileServices](Microsoft-ClassicStorage-storageAccounts-fileServices-metrics.md)
* [Microsoft.ClassicStorage/storageAccounts/queueServices](Microsoft-ClassicStorage-storageAccounts-queueServices-metrics.md)
* [Microsoft.ClassicStorage/storageAccounts/tableServices](Microsoft-ClassicStorage-storageAccounts-tableServices-metrics.md)

  
### Microsoft.Cloudtest<a name="microsoftcloudtesthostedpools"></a><a name="microsoftcloudtestpools"></a>
  
  * [Microsoft.Cloudtest/hostedpools](Microsoft-Cloudtest-hostedpools-metrics.md)
* [Microsoft.Cloudtest/pools](Microsoft-Cloudtest-pools-metrics.md)

  
### Microsoft.ClusterStor<a name="microsoftclusterstornodes"></a>
  
  * [Microsoft.ClusterStor/nodes](Microsoft-ClusterStor-nodes-metrics.md)

  
### Microsoft.CodeSigning<a name="microsoftcodesigningcodesigningaccounts"></a>
  
  * [Microsoft.CodeSigning/codesigningaccounts](Microsoft-CodeSigning-codesigningaccounts-metrics.md)

  
### Microsoft.CognitiveServices<a name="microsoftcognitiveservicesaccounts"></a>
  
  * [Microsoft.CognitiveServices/accounts](Microsoft-CognitiveServices-accounts-metrics.md)

  
### Microsoft.Communication<a name="microsoftcommunicationcommunicationservices"></a>
  
  * [Microsoft.Communication/CommunicationServices](Microsoft-Communication-CommunicationServices-metrics.md)

  
### Microsoft.Compute<a name="microsoftcomputecloudservices"></a><a name="microsoftcomputecloudservicesroles"></a><a name="microsoftcomputevirtualmachines"></a><a name="microsoftcomputevirtualmachinescalesets"></a><a name="microsoftcomputevirtualmachinescalesetsvirtualmachines"></a>
  
  * [Microsoft.Compute/cloudservices](Microsoft-Compute-cloudservices-metrics.md)
* [Microsoft.Compute/cloudServices/roles](Microsoft-Compute-cloudServices-roles-metrics.md)
* [Microsoft.Compute/virtualMachines](Microsoft-Compute-virtualMachines-metrics.md)
* [Microsoft.Compute/virtualmachineScaleSets](Microsoft-Compute-virtualmachineScaleSets-metrics.md)
* [Microsoft.Compute/virtualMachineScaleSets/virtualMachines](Microsoft-Compute-virtualMachineScaleSets-virtualMachines-metrics.md)

  
### microsoft.compute<a name="microsoftcomputedisks"></a>
  
  * [microsoft.compute/disks](microsoft-compute-disks-metrics.md)

  
### Microsoft.ConnectedCache<a name="microsoftconnectedcachecachenodes"></a><a name="microsoftconnectedcacheenterprisemcccustomers"></a><a name="microsoftconnectedcacheispcustomers"></a>
  
  * [Microsoft.ConnectedCache/CacheNodes](Microsoft-ConnectedCache-CacheNodes-metrics.md)
* [Microsoft.ConnectedCache/enterpriseMccCustomers](Microsoft-ConnectedCache-enterpriseMccCustomers-metrics.md)
* [Microsoft.ConnectedCache/ispCustomers](Microsoft-ConnectedCache-ispCustomers-metrics.md)

  
### Microsoft.ConnectedVehicle<a name="microsoftconnectedvehicleplatformaccounts"></a>
  
  * [Microsoft.ConnectedVehicle/platformAccounts](Microsoft-ConnectedVehicle-platformAccounts-metrics.md)

  
### Microsoft.ContainerInstance<a name="microsoftcontainerinstancecontainergroups"></a><a name="microsoftcontainerinstancecontainerscalesets"></a>
  
  * [Microsoft.ContainerInstance/containerGroups](Microsoft-ContainerInstance-containerGroups-metrics.md)
* [Microsoft.ContainerInstance/containerScaleSets](Microsoft-ContainerInstance-containerScaleSets-metrics.md)

  
### Microsoft.ContainerRegistry<a name="microsoftcontainerregistryregistries"></a>
  
  * [Microsoft.ContainerRegistry/registries](Microsoft-ContainerRegistry-registries-metrics.md)

  
### Microsoft.ContainerService<a name="microsoftcontainerservicemanagedclusters"></a>
  
  * [Microsoft.ContainerService/managedClusters](Microsoft-ContainerService-managedClusters-metrics.md)

  
### Microsoft.CustomProviders<a name="microsoftcustomprovidersresourceproviders"></a>
  
  * [Microsoft.CustomProviders/resourceproviders](Microsoft-CustomProviders-resourceproviders-metrics.md)

  
### Microsoft.Dashboard<a name="microsoftdashboardgrafana"></a>
  
  * [Microsoft.Dashboard/grafana](Microsoft-Dashboard-grafana-metrics.md)

  
### Microsoft.DataBoxEdge<a name="microsoftdataboxedgedataboxedgedevices"></a>
  
  * [Microsoft.DataBoxEdge/dataBoxEdgeDevices](Microsoft-DataBoxEdge-dataBoxEdgeDevices-metrics.md)

  
### Microsoft.DataFactory<a name="microsoftdatafactorydatafactories"></a><a name="microsoftdatafactoryfactories"></a>
  
  * [Microsoft.DataFactory/datafactories](Microsoft-DataFactory-datafactories-metrics.md)
* [Microsoft.DataFactory/factories](Microsoft-DataFactory-factories-metrics.md)

  
### Microsoft.DataLakeAnalytics<a name="microsoftdatalakeanalyticsaccounts"></a>
  
  * [Microsoft.DataLakeAnalytics/accounts](Microsoft-DataLakeAnalytics-accounts-metrics.md)

  
### Microsoft.DataLakeStore<a name="microsoftdatalakestoreaccounts"></a>
  
  * [Microsoft.DataLakeStore/accounts](Microsoft-DataLakeStore-accounts-metrics.md)

  
### Microsoft.DataProtection<a name="microsoftdataprotectionbackupvaults"></a>
  
  * [Microsoft.DataProtection/BackupVaults](Microsoft-DataProtection-BackupVaults-metrics.md)

  
### Microsoft.DataShare<a name="microsoftdatashareaccounts"></a>
  
  * [Microsoft.DataShare/accounts](Microsoft-DataShare-accounts-metrics.md)

  
### Microsoft.DBforMariaDB<a name="microsoftdbformariadbservers"></a>
  
  * [Microsoft.DBforMariaDB/servers](Microsoft-DBforMariaDB-servers-metrics.md)

  
### Microsoft.DBforMySQL<a name="microsoftdbformysqlflexibleservers"></a><a name="microsoftdbformysqlservers"></a>
  
  * [Microsoft.DBforMySQL/flexibleServers](Microsoft-DBforMySQL-flexibleServers-metrics.md)
* [Microsoft.DBforMySQL/servers](Microsoft-DBforMySQL-servers-metrics.md)

  
### Microsoft.DBforPostgreSQL<a name="microsoftdbforpostgresqlflexibleservers"></a><a name="microsoftdbforpostgresqlservers"></a><a name="microsoftdbforpostgresqlserversv2"></a>
  
  * [Microsoft.DBforPostgreSQL/flexibleServers](Microsoft-DBforPostgreSQL-flexibleServers-metrics.md)
* [Microsoft.DBforPostgreSQL/servers](Microsoft-DBforPostgreSQL-servers-metrics.md)
* [Microsoft.DBforPostgreSQL/serversv2](Microsoft-DBforPostgreSQL-serversv2-metrics.md)

  
### Microsoft.DBForPostgreSQL<a name="microsoftdbforpostgresqlservergroupsv2"></a>
  
  * [Microsoft.DBForPostgreSQL/serverGroupsv2](Microsoft-DBForPostgreSQL-serverGroupsv2-metrics.md)

  
### Microsoft.DevCenter<a name="microsoftdevcenterdevcenters"></a>
  
  * [Microsoft.DevCenter/devcenters](Microsoft-DevCenter-devcenters-metrics.md)

  
### Microsoft.Devices<a name="microsoftdevicesiothubs"></a><a name="microsoftdevicesprovisioningservices"></a>
  
  * [Microsoft.Devices/IotHubs](Microsoft-Devices-IotHubs-metrics.md)
* [Microsoft.Devices/provisioningServices](Microsoft-Devices-provisioningServices-metrics.md)

  
### Microsoft.DigitalTwins<a name="microsoftdigitaltwinsdigitaltwinsinstances"></a>
  
  * [Microsoft.DigitalTwins/digitalTwinsInstances](Microsoft-DigitalTwins-digitalTwinsInstances-metrics.md)

  
### Microsoft.DocumentDB<a name="microsoftdocumentdbcassandraclusters"></a><a name="microsoftdocumentdbdatabaseaccounts"></a><a name="microsoftdocumentdbmongoclusters"></a>
  
  * [Microsoft.DocumentDB/cassandraClusters](Microsoft-DocumentDB-cassandraClusters-metrics.md)
* [Microsoft.DocumentDB/DatabaseAccounts](Microsoft-DocumentDB-DatabaseAccounts-metrics.md)
* [Microsoft.DocumentDB/mongoClusters](Microsoft-DocumentDB-mongoClusters-metrics.md)

  
### microsoft.edgezones<a name="microsoftedgezonesedgezones"></a>
  
  * [microsoft.edgezones/edgezones](microsoft-edgezones-edgezones-metrics.md)

  
### Microsoft.EventGrid<a name="microsofteventgriddomains"></a><a name="microsofteventgrideventsubscriptions"></a><a name="microsofteventgridextensiontopics"></a><a name="microsofteventgridnamespaces"></a><a name="microsofteventgridpartnernamespaces"></a><a name="microsofteventgridpartnertopics"></a><a name="microsofteventgridsystemtopics"></a><a name="microsofteventgridtopics"></a>
  
  * [Microsoft.EventGrid/domains](Microsoft-EventGrid-domains-metrics.md)
* [Microsoft.EventGrid/eventSubscriptions](Microsoft-EventGrid-eventSubscriptions-metrics.md)
* [Microsoft.EventGrid/extensionTopics](Microsoft-EventGrid-extensionTopics-metrics.md)
* [Microsoft.EventGrid/namespaces](Microsoft-EventGrid-namespaces-metrics.md)
* [Microsoft.EventGrid/partnerNamespaces](Microsoft-EventGrid-partnerNamespaces-metrics.md)
* [Microsoft.EventGrid/partnerTopics](Microsoft-EventGrid-partnerTopics-metrics.md)
* [Microsoft.EventGrid/systemTopics](Microsoft-EventGrid-systemTopics-metrics.md)
* [Microsoft.EventGrid/topics](Microsoft-EventGrid-topics-metrics.md)

  
### Microsoft.EventHub<a name="microsofteventhubclusters"></a><a name="microsofteventhubnamespaces"></a>
  
  * [Microsoft.EventHub/clusters](Microsoft-EventHub-clusters-metrics.md)
* [Microsoft.EventHub/Namespaces](Microsoft-EventHub-Namespaces-metrics.md)

  
### Microsoft.HDInsight<a name="microsofthdinsightclusters"></a>
  
  * [Microsoft.HDInsight/clusters](Microsoft-HDInsight-clusters-metrics.md)

  
### Microsoft.HealthcareApis<a name="microsofthealthcareapisservices"></a><a name="microsofthealthcareapisworkspacesdicomservices"></a><a name="microsofthealthcareapisworkspacesfhirservices"></a><a name="microsofthealthcareapisworkspacesiotconnectors"></a>
  
  * [Microsoft.HealthcareApis/services](Microsoft-HealthcareApis-services-metrics.md)
* [Microsoft.HealthcareApis/workspaces/dicomservices](Microsoft-HealthcareApis-workspaces-dicomservices-metrics.md)
* [Microsoft.HealthcareApis/workspaces/fhirservices](Microsoft-HealthcareApis-workspaces-fhirservices-metrics.md)
* [Microsoft.HealthcareApis/workspaces/iotconnectors](Microsoft-HealthcareApis-workspaces-iotconnectors-metrics.md)

  
### Microsoft.HealthModel<a name="microsofthealthmodelhealthmodels"></a>
  
  * [Microsoft.HealthModel/healthmodels](Microsoft-HealthModel-healthmodels-metrics.md)

  
### Microsoft.HybridContainerService<a name="microsofthybridcontainerserviceprovisionedclusters"></a>
  
  * [Microsoft.HybridContainerService/provisionedClusters](Microsoft-HybridContainerService-provisionedClusters-metrics.md)

  
### microsoft.hybridnetwork<a name="microsofthybridnetworknetworkfunctions"></a><a name="microsofthybridnetworkvirtualnetworkfunctions"></a>
  
  * [microsoft.hybridnetwork/networkfunctions](microsoft-hybridnetwork-networkfunctions-metrics.md)
* [microsoft.hybridnetwork/virtualnetworkfunctions](microsoft-hybridnetwork-virtualnetworkfunctions-metrics.md)

  
### microsoft.insights<a name="microsoftinsightsautoscalesettings"></a><a name="microsoftinsightscomponents"></a>
  
  * [microsoft.insights/autoscalesettings](microsoft-insights-autoscalesettings-metrics.md)
* [microsoft.insights/components](microsoft-insights-components-metrics.md)

  
### Microsoft.IoTCentral<a name="microsoftiotcentraliotapps"></a>
  
  * [Microsoft.IoTCentral/IoTApps](Microsoft-IoTCentral-IoTApps-metrics.md)

  
### microsoft.keyvault<a name="microsoftkeyvaultmanagedhsms"></a>
  
  * [microsoft.keyvault/managedhsms](microsoft-keyvault-managedhsms-metrics.md)

  
### Microsoft.KeyVault<a name="microsoftkeyvaultvaults"></a>
  
  * [Microsoft.KeyVault/vaults](Microsoft-KeyVault-vaults-metrics.md)

  
### microsoft.kubernetes<a name="microsoftkubernetesconnectedclusters"></a>
  
  * [microsoft.kubernetes/connectedClusters](microsoft-kubernetes-connectedClusters-metrics.md)

  
### microsoft.kubernetesconfiguration<a name="microsoftkubernetesconfigurationextensions"></a>
  
  * [microsoft.kubernetesconfiguration/extensions](microsoft-kubernetesconfiguration-extensions-metrics.md)

  
### Microsoft.Kusto<a name="microsoftkustoclusters"></a>
  
  * [Microsoft.Kusto/clusters](Microsoft-Kusto-clusters-metrics.md)

  
### Microsoft.Logic<a name="microsoftlogicintegrationserviceenvironments"></a><a name="microsoftlogicworkflows"></a>
  
  * [Microsoft.Logic/IntegrationServiceEnvironments](Microsoft-Logic-IntegrationServiceEnvironments-metrics.md)
* [Microsoft.Logic/Workflows](Microsoft-Logic-Workflows-metrics.md)

  
### Microsoft.MachineLearningServices<a name="microsoftmachinelearningservicesworkspaces"></a><a name="microsoftmachinelearningservicesworkspacesonlineendpoints"></a><a name="microsoftmachinelearningservicesworkspacesonlineendpointsdeployments"></a>
  
  * [Microsoft.MachineLearningServices/workspaces](Microsoft-MachineLearningServices-workspaces-metrics.md)
* [Microsoft.MachineLearningServices/workspaces/onlineEndpoints](Microsoft-MachineLearningServices-workspaces-onlineEndpoints-metrics.md)
* [Microsoft.MachineLearningServices/workspaces/onlineEndpoints/deployments](Microsoft-MachineLearningServices-workspaces-onlineEndpoints-deployments-metrics.md)

  
### Microsoft.ManagedNetworkFabric<a name="microsoftmanagednetworkfabricinternetgateways"></a><a name="microsoftmanagednetworkfabricl3isolationdomains"></a><a name="microsoftmanagednetworkfabricnetworkdevices"></a>
  
  * [Microsoft.ManagedNetworkFabric/internetGateways](Microsoft-ManagedNetworkFabric-internetGateways-metrics.md)
* [Microsoft.ManagedNetworkFabric/l3IsolationDomains](Microsoft-ManagedNetworkFabric-l3IsolationDomains-metrics.md)
* [Microsoft.ManagedNetworkFabric/networkDevices](Microsoft-ManagedNetworkFabric-networkDevices-metrics.md)

  
### Microsoft.Maps<a name="microsoftmapsaccounts"></a>
  
  * [Microsoft.Maps/accounts](Microsoft-Maps-accounts-metrics.md)

  
### Microsoft.Media<a name="microsoftmediamediaservices"></a><a name="microsoftmediamediaservicesliveevents"></a><a name="microsoftmediamediaservicesstreamingendpoints"></a><a name="microsoftmediavideoanalyzers"></a>
  
  * [Microsoft.Media/mediaservices](Microsoft-Media-mediaservices-metrics.md)
* [Microsoft.Media/mediaservices/liveEvents](Microsoft-Media-mediaservices-liveEvents-metrics.md)
* [Microsoft.Media/mediaservices/streamingEndpoints](Microsoft-Media-mediaservices-streamingEndpoints-metrics.md)
* [Microsoft.Media/videoanalyzers](Microsoft-Media-videoanalyzers-metrics.md)

  
### Microsoft.MixedReality<a name="microsoftmixedrealityremoterenderingaccounts"></a><a name="microsoftmixedrealityspatialanchorsaccounts"></a>
  
  * [Microsoft.MixedReality/remoteRenderingAccounts](Microsoft-MixedReality-remoteRenderingAccounts-metrics.md)
* [Microsoft.MixedReality/spatialAnchorsAccounts](Microsoft-MixedReality-spatialAnchorsAccounts-metrics.md)

  
### Microsoft.MobileNetwork<a name="microsoftmobilenetworkpacketcorecontrolplanes"></a><a name="microsoftmobilenetworkpacketcorecontrolplanespacketcoredataplanes"></a>
  
  * [Microsoft.MobileNetwork/packetcorecontrolplanes](Microsoft-MobileNetwork-packetcorecontrolplanes-metrics.md)
* [Microsoft.MobileNetwork/packetcorecontrolplanes/packetcoredataplanes](Microsoft-MobileNetwork-packetcorecontrolplanes-packetcoredataplanes-metrics.md)

  
### Microsoft.Monitor<a name="microsoftmonitoraccounts"></a>
  
  * [Microsoft.Monitor/accounts](Microsoft-Monitor-accounts-metrics.md)

  
### Microsoft.NetApp<a name="microsoftnetappnetappaccountscapacitypools"></a><a name="microsoftnetappnetappaccountscapacitypoolsvolumes"></a>
  
  * [Microsoft.NetApp/netAppAccounts/capacityPools](Microsoft-NetApp-netAppAccounts-capacityPools-metrics.md)
* [Microsoft.NetApp/netAppAccounts/capacityPools/volumes](Microsoft-NetApp-netAppAccounts-capacityPools-volumes-metrics.md)

  
### Microsoft.Network<a name="microsoftnetworkapplicationgateways"></a><a name="microsoftnetworkazurefirewalls"></a><a name="microsoftnetworkconnections"></a><a name="microsoftnetworkdnsforwardingrulesets"></a><a name="microsoftnetworkdnsresolvers"></a><a name="microsoftnetworkdnszones"></a><a name="microsoftnetworkexpressroutecircuits"></a><a name="microsoftnetworkexpressroutecircuitspeerings"></a><a name="microsoftnetworkexpressrouteports"></a><a name="microsoftnetworkfrontdoors"></a><a name="microsoftnetworkloadbalancers"></a><a name="microsoftnetworknatgateways"></a><a name="microsoftnetworknetworkinterfaces"></a><a name="microsoftnetworknetworkmanagersipampools"></a><a name="microsoftnetworknetworkwatchersconnectionmonitors"></a><a name="microsoftnetworkprivatednszones"></a><a name="microsoftnetworkprivateendpoints"></a><a name="microsoftnetworkprivatelinkservices"></a><a name="microsoftnetworkpublicipaddresses"></a><a name="microsoftnetworkpublicipprefixes"></a><a name="microsoftnetworktrafficmanagerprofiles"></a><a name="microsoftnetworkvirtualhubs"></a><a name="microsoftnetworkvirtualnetworks"></a><a name="microsoftnetworkvirtualrouters"></a>
  
  * [Microsoft.Network/applicationgateways](Microsoft-Network-applicationgateways-metrics.md)
* [Microsoft.Network/azureFirewalls](Microsoft-Network-azureFirewalls-metrics.md)
* [Microsoft.Network/connections](Microsoft-Network-connections-metrics.md)
* [Microsoft.Network/dnsForwardingRulesets](Microsoft-Network-dnsForwardingRulesets-metrics.md)
* [Microsoft.Network/dnsResolvers](Microsoft-Network-dnsResolvers-metrics.md)
* [Microsoft.Network/dnszones](Microsoft-Network-dnszones-metrics.md)
* [Microsoft.Network/expressRouteCircuits](Microsoft-Network-expressRouteCircuits-metrics.md)
* [Microsoft.Network/expressRouteCircuits/peerings](Microsoft-Network-expressRouteCircuits-peerings-metrics.md)
* [Microsoft.Network/expressRoutePorts](Microsoft-Network-expressRoutePorts-metrics.md)
* [Microsoft.Network/frontdoors](Microsoft-Network-frontdoors-metrics.md)
* [Microsoft.Network/loadBalancers](Microsoft-Network-loadBalancers-metrics.md)
* [Microsoft.Network/natGateways](Microsoft-Network-natGateways-metrics.md)
* [Microsoft.Network/networkInterfaces](Microsoft-Network-networkInterfaces-metrics.md)
* [Microsoft.Network/networkManagers/ipamPools](Microsoft-Network-networkManagers-ipamPools-metrics.md)
* [Microsoft.Network/networkWatchers/connectionMonitors](Microsoft-Network-networkWatchers-connectionMonitors-metrics.md)
* [Microsoft.Network/privateDnsZones](Microsoft-Network-privateDnsZones-metrics.md)
* [Microsoft.Network/privateEndpoints](Microsoft-Network-privateEndpoints-metrics.md)
* [Microsoft.Network/privateLinkServices](Microsoft-Network-privateLinkServices-metrics.md)
* [Microsoft.Network/publicIPAddresses](Microsoft-Network-publicIPAddresses-metrics.md)
* [Microsoft.Network/publicIPPrefixes](Microsoft-Network-publicIPPrefixes-metrics.md)
* [Microsoft.Network/trafficManagerProfiles](Microsoft-Network-trafficManagerProfiles-metrics.md)
* [Microsoft.Network/virtualHubs](Microsoft-Network-virtualHubs-metrics.md)
* [Microsoft.Network/virtualNetworks](Microsoft-Network-virtualNetworks-metrics.md)
* [Microsoft.Network/virtualRouters](Microsoft-Network-virtualRouters-metrics.md)

  
### microsoft.network<a name="microsoftnetworkbastionhosts"></a><a name="microsoftnetworkexpressroutegateways"></a><a name="microsoftnetworkp2svpngateways"></a><a name="microsoftnetworkvirtualnetworkgateways"></a><a name="microsoftnetworkvpngateways"></a>
  
  * [microsoft.network/bastionHosts](microsoft-network-bastionHosts-metrics.md)
* [microsoft.network/expressroutegateways](microsoft-network-expressroutegateways-metrics.md)
* [microsoft.network/p2svpngateways](microsoft-network-p2svpngateways-metrics.md)
* [microsoft.network/virtualnetworkgateways](microsoft-network-virtualnetworkgateways-metrics.md)
* [microsoft.network/vpngateways](microsoft-network-vpngateways-metrics.md)

  
### Microsoft.NetworkAnalytics<a name="microsoftnetworkanalyticsdataconnectors"></a>
  
  * [Microsoft.NetworkAnalytics/DataConnectors](Microsoft-NetworkAnalytics-DataConnectors-metrics.md)

  
### Microsoft.NetworkCloud<a name="microsoftnetworkcloudbaremetalmachines"></a><a name="microsoftnetworkcloudclusters"></a><a name="microsoftnetworkcloudstorageappliances"></a>
  
  * [Microsoft.NetworkCloud/bareMetalMachines](Microsoft-NetworkCloud-bareMetalMachines-metrics.md)
* [Microsoft.NetworkCloud/clusters](Microsoft-NetworkCloud-clusters-metrics.md)
* [Microsoft.NetworkCloud/storageAppliances](Microsoft-NetworkCloud-storageAppliances-metrics.md)

  
### Microsoft.NetworkFunction<a name="microsoftnetworkfunctionazuretrafficcollectors"></a>
  
  * [Microsoft.NetworkFunction/azureTrafficCollectors](Microsoft-NetworkFunction-azureTrafficCollectors-metrics.md)

  
### Microsoft.NotificationHubs<a name="microsoftnotificationhubsnamespacesnotificationhubs"></a>
  
  * [Microsoft.NotificationHubs/namespaces/notificationHubs](Microsoft-NotificationHubs-namespaces-notificationHubs-metrics.md)

  
### Microsoft.OperationalInsights<a name="microsoftoperationalinsightsworkspaces"></a>
  
  * [Microsoft.OperationalInsights/workspaces](Microsoft-OperationalInsights-workspaces-metrics.md)

  
### Microsoft.Orbital<a name="microsoftorbitalcontactprofiles"></a><a name="microsoftorbitall2connections"></a><a name="microsoftorbitalspacecrafts"></a><a name="microsoftorbitalterminals"></a>
  
  * [Microsoft.Orbital/contactProfiles](Microsoft-Orbital-contactProfiles-metrics.md)
* [Microsoft.Orbital/l2Connections](Microsoft-Orbital-l2Connections-metrics.md)
* [Microsoft.Orbital/spacecrafts](Microsoft-Orbital-spacecrafts-metrics.md)
* [Microsoft.Orbital/terminals](Microsoft-Orbital-terminals-metrics.md)

  
### Microsoft.Peering<a name="microsoftpeeringpeerings"></a><a name="microsoftpeeringpeeringservices"></a>
  
  * [Microsoft.Peering/peerings](Microsoft-Peering-peerings-metrics.md)
* [Microsoft.Peering/peeringServices](Microsoft-Peering-peeringServices-metrics.md)

  
### Microsoft.PlayFab<a name="microsoftplayfabtitles"></a>
  
  * [Microsoft.PlayFab/titles](Microsoft-PlayFab-titles-metrics.md)

  
### Microsoft.PowerBIDedicated<a name="microsoftpowerbidedicatedcapacities"></a>
  
  * [Microsoft.PowerBIDedicated/capacities](Microsoft-PowerBIDedicated-capacities-metrics.md)

  
### microsoft.purview<a name="microsoftpurviewaccounts"></a>
  
  * [microsoft.purview/accounts](microsoft-purview-accounts-metrics.md)

  
### Microsoft.RecoveryServices<a name="microsoftrecoveryservicesvaults"></a>
  
  * [Microsoft.RecoveryServices/Vaults](Microsoft-RecoveryServices-Vaults-metrics.md)

  
### Microsoft.Relay<a name="microsoftrelaynamespaces"></a>
  
  * [Microsoft.Relay/namespaces](Microsoft-Relay-namespaces-metrics.md)

  
### microsoft.resources<a name="microsoftresourcessubscriptions"></a>
  
  * [microsoft.resources/subscriptions](microsoft-resources-subscriptions-metrics.md)

  
### Microsoft.Search<a name="microsoftsearchsearchservices"></a>
  
  * [Microsoft.Search/searchServices](Microsoft-Search-searchServices-metrics.md)

  
### microsoft.securitydetonation<a name="microsoftsecuritydetonationchambers"></a>
  
  * [microsoft.securitydetonation/chambers](microsoft-securitydetonation-chambers-metrics.md)

  
### Microsoft.SecurityDetonation<a name="microsoftsecuritydetonationsecuritydetonationchambers"></a>
  
  * [Microsoft.SecurityDetonation/SecurityDetonationChambers](Microsoft-SecurityDetonation-SecurityDetonationChambers-metrics.md)

  
### Microsoft.ServiceBus<a name="microsoftservicebusnamespaces"></a>
  
  * [Microsoft.ServiceBus/Namespaces](Microsoft-ServiceBus-Namespaces-metrics.md)

  
### Microsoft.ServiceNetworking<a name="microsoftservicenetworkingtrafficcontrollers"></a>
  
  * [Microsoft.ServiceNetworking/trafficControllers](Microsoft-ServiceNetworking-trafficControllers-metrics.md)

  
### Microsoft.SignalRService<a name="microsoftsignalrservicesignalr"></a><a name="microsoftsignalrservicesignalrreplicas"></a><a name="microsoftsignalrservicewebpubsub"></a><a name="microsoftsignalrservicewebpubsubreplicas"></a>
  
  * [Microsoft.SignalRService/SignalR](Microsoft-SignalRService-SignalR-metrics.md)
* [Microsoft.SignalRService/SignalR/replicas](Microsoft-SignalRService-SignalR-replicas-metrics.md)
* [Microsoft.SignalRService/WebPubSub](Microsoft-SignalRService-WebPubSub-metrics.md)
* [Microsoft.SignalRService/WebPubSub/replicas](Microsoft-SignalRService-WebPubSub-replicas-metrics.md)

  
### microsoft.singularity<a name="microsoftsingularityaccounts"></a>
  
  * [microsoft.singularity/accounts](microsoft-singularity-accounts-metrics.md)

  
### Microsoft.Sql<a name="microsoftsqlmanagedinstances"></a><a name="microsoftsqlserversdatabases"></a><a name="microsoftsqlserverselasticpools"></a><a name="microsoftsqlserversjobagents"></a>
  
  * [Microsoft.Sql/managedInstances](Microsoft-Sql-managedInstances-metrics.md)
* [Microsoft.Sql/servers/databases](Microsoft-Sql-servers-databases-metrics.md)
* [Microsoft.Sql/servers/elasticpools](Microsoft-Sql-servers-elasticpools-metrics.md)
* [Microsoft.Sql/servers/jobAgents](Microsoft-Sql-servers-jobAgents-metrics.md)

  
### Microsoft.Storage<a name="microsoftstoragestorageaccounts"></a><a name="microsoftstoragestorageaccountsblobservices"></a><a name="microsoftstoragestorageaccountsfileservices"></a><a name="microsoftstoragestorageaccountsobjectreplicationpolicies"></a><a name="microsoftstoragestorageaccountsqueueservices"></a><a name="microsoftstoragestorageaccountsstoragetasks"></a><a name="microsoftstoragestorageaccountstableservices"></a><a name="microsoftstoragestoragetasks"></a>
  
  * [Microsoft.Storage/storageAccounts](Microsoft-Storage-storageAccounts-metrics.md)
* [Microsoft.Storage/storageAccounts/blobServices](Microsoft-Storage-storageAccounts-blobServices-metrics.md)
* [Microsoft.Storage/storageAccounts/fileServices](Microsoft-Storage-storageAccounts-fileServices-metrics.md)
* [Microsoft.Storage/storageAccounts/objectReplicationPolicies](Microsoft-Storage-storageAccounts-objectReplicationPolicies-metrics.md)
* [Microsoft.Storage/storageAccounts/queueServices](Microsoft-Storage-storageAccounts-queueServices-metrics.md)
* [Microsoft.Storage/storageAccounts/storageTasks](Microsoft-Storage-storageAccounts-storageTasks-metrics.md)
* [Microsoft.Storage/storageAccounts/tableServices](Microsoft-Storage-storageAccounts-tableServices-metrics.md)
* [Microsoft.Storage/storageTasks](Microsoft-Storage-storageTasks-metrics.md)

  
### Microsoft.StorageActions<a name="microsoftstorageactionsstoragetasks"></a>
  
  * [Microsoft.StorageActions/storageTasks](Microsoft-StorageActions-storageTasks-metrics.md)

  
### Microsoft.StorageCache<a name="microsoftstoragecacheamlfilesystems"></a><a name="microsoftstoragecachecaches"></a>
  
  * [Microsoft.StorageCache/amlFilesystems](Microsoft-StorageCache-amlFilesystems-metrics.md)
* [Microsoft.StorageCache/caches](Microsoft-StorageCache-caches-metrics.md)

  
### Microsoft.StorageMover<a name="microsoftstoragemoverstoragemovers"></a>
  
  * [Microsoft.StorageMover/storageMovers](Microsoft-StorageMover-storageMovers-metrics.md)

  
### Microsoft.StorageSync<a name="microsoftstoragesyncstoragesyncservices"></a>
  
  * [Microsoft.StorageSync/storageSyncServices](Microsoft-StorageSync-storageSyncServices-metrics.md)

  
### Microsoft.StorageTasks<a name="microsoftstoragetasksstoragetasks"></a>
  
  * [Microsoft.StorageTasks/storageTasks](Microsoft-StorageTasks-storageTasks-metrics.md)

  
### Microsoft.StreamAnalytics<a name="microsoftstreamanalyticsstreamingjobs"></a>
  
  * [Microsoft.StreamAnalytics/streamingjobs](Microsoft-StreamAnalytics-streamingjobs-metrics.md)

  
### Microsoft.Synapse<a name="microsoftsynapseworkspaces"></a><a name="microsoftsynapseworkspacesbigdatapools"></a><a name="microsoftsynapseworkspaceskustopools"></a><a name="microsoftsynapseworkspacesscopepools"></a><a name="microsoftsynapseworkspacessqlpools"></a>
  
  * [Microsoft.Synapse/workspaces](Microsoft-Synapse-workspaces-metrics.md)
* [Microsoft.Synapse/workspaces/bigDataPools](Microsoft-Synapse-workspaces-bigDataPools-metrics.md)
* [Microsoft.Synapse/workspaces/kustoPools](Microsoft-Synapse-workspaces-kustoPools-metrics.md)
* [Microsoft.Synapse/workspaces/scopePools](Microsoft-Synapse-workspaces-scopePools-metrics.md)
* [Microsoft.Synapse/workspaces/sqlPools](Microsoft-Synapse-workspaces-sqlPools-metrics.md)

  
### Microsoft.TimeSeriesInsights<a name="microsofttimeseriesinsightsenvironments"></a><a name="microsofttimeseriesinsightsenvironmentseventsources"></a>
  
  * [Microsoft.TimeSeriesInsights/environments](Microsoft-TimeSeriesInsights-environments-metrics.md)
* [Microsoft.TimeSeriesInsights/environments/eventsources](Microsoft-TimeSeriesInsights-environments-eventsources-metrics.md)

  
### Microsoft.VoiceServices<a name="microsoftvoiceservicescommunicationsgateways"></a>
  
  * [Microsoft.VoiceServices/CommunicationsGateways](Microsoft-VoiceServices-CommunicationsGateways-metrics.md)

  
### Microsoft.Web<a name="microsoftwebcontainerapps"></a><a name="microsoftwebhostingenvironments"></a><a name="microsoftwebhostingenvironmentsmultirolepools"></a><a name="microsoftwebhostingenvironmentsworkerpools"></a><a name="microsoftwebserverfarms"></a><a name="microsoftwebsites"></a><a name="microsoftwebsitesslots"></a><a name="microsoftwebstaticsites"></a>
  
  * [Microsoft.Web/containerapps](Microsoft-Web-containerapps-metrics.md)
* [Microsoft.Web/hostingEnvironments](Microsoft-Web-hostingEnvironments-metrics.md)
* [Microsoft.Web/hostingenvironments/multirolepools](Microsoft-Web-hostingenvironments-multirolepools-metrics.md)
* [Microsoft.Web/hostingenvironments/workerpools](Microsoft-Web-hostingenvironments-workerpools-metrics.md)
* [Microsoft.Web/serverfarms](Microsoft-Web-serverfarms-metrics.md)
* [Microsoft.Web/sites](Microsoft-Web-sites-metrics.md)
* [Microsoft.Web/sites/slots](Microsoft-Web-sites-slots-metrics.md)
* [Microsoft.Web/staticsites](Microsoft-Web-staticsites-metrics.md)

  
### NGINX.NGINXPLUS<a name="nginxnginxplusnginxdeployments"></a>
  
  * [NGINX.NGINXPLUS/nginxDeployments](NGINX-NGINXPLUS-nginxDeployments-metrics.md)

  
### Wandisco.Fusion<a name="wandiscofusionmigrators"></a><a name="wandiscofusionmigratorsdatatransferagents"></a><a name="wandiscofusionmigratorslivedatamigrations"></a><a name="wandiscofusionmigratorsmetadatamigrations"></a>
  
  * [Wandisco.Fusion/migrators](Wandisco-Fusion-migrators-metrics.md)
* [Wandisco.Fusion/migrators/dataTransferAgents](Wandisco-Fusion-migrators-dataTransferAgents-metrics.md)
* [Wandisco.Fusion/migrators/liveDataMigrations](Wandisco-Fusion-migrators-liveDataMigrations-metrics.md)
* [Wandisco.Fusion/migrators/metadataMigrations](Wandisco-Fusion-migrators-metadataMigrations-metrics.md)

  

## Next steps

- [Read about metrics in Azure Monitor](/azure/azure-monitor/data-platform)
- [Create alerts on metrics](/azure/azure-monitor/alerts/alerts-overview)
- [Export metrics to storage, Event Hub, or Log Analytics](/azure/azure-monitor/essentials/platform-logs-overview)
