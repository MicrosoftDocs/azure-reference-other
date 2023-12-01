---
title: Supported categories for Azure Monitor resource logs
description: Understand the supported services and event schemas for Azure Monitor resource logs.
author: EdB-MSFT
ms.topic: reference
ms.service: azure-monitor
ms.date: 12/01/2023
ms.author: edbaynash
ms.reviewer: lualderm

---

# Supported categories for Azure Monitor resource logs

> [!NOTE]
> This list is largely auto-generated. Any modification made to this list via GitHub might be written over without warning. Contact the author of this article for details on how to make permanent updates.

[Azure Monitor resource logs](/azure/azure-monitor/essentials/platform-logs-overview) are logs emitted by Azure services that describe the operation of those services or resources. All resource logs available through Azure Monitor share a common top-level schema. Each service has the flexibility to emit unique properties for its own events.

Resource logs were previously known as diagnostic logs. The name was changed in October 2019 as the types of logs gathered by Azure Monitor shifted to include more than just the Azure resource.

A combination of the resource type (available in the `resourceId` property) and the category uniquely identifies a schema. There's a common schema for all resource logs with service-specific fields then added for different log categories. For more information, see [Common and service-specific schema for Azure resource logs](/azure/azure-monitor/essentials/resource-logs-schema).

## Costs

[Azure Monitor Log Analytics](https://azure.microsoft.com/pricing/details/monitor/), [Azure Storage](https://azure.microsoft.com/product-categories/storage/), [Azure Event Hubs](https://azure.microsoft.com/pricing/details/event-hubs/), and partners who integrate directly with Azure Monitor (for example, [Datadog](/azure/partner-solutions/datadog/overview)) have costs associated with ingesting data and storing data. Check the pricing pages linked in the previous sentence to understand the costs for those services. Resource logs are just one type of data that you can send to those locations.  

In addition, there might be costs to export some categories of resource logs to those locations. Logs with possible export costs are listed in the next section. Select the links below to see which log categories have export costs associated with them. For more information on export pricing, see the **Platform Logs** section on the [Azure Monitor pricing page](https://azure.microsoft.com/pricing/details/monitor/).

## Supported log categories per resource type

Following is a list of the types of logs available for each resource type. 

Some categories might be supported only for specific types of resources. See the resource-specific documentation if you feel you're missing a resource. For example, Microsoft.Sql/servers/databases categories aren't available for all types of databases. For more information, see [information on SQL Database diagnostic logging](/azure/azure-sql/database/metrics-diagnostic-telemetry-logging-streaming-export-configure). 

If you think something is missing, you can open a GitHub comment at the bottom of this article.  

## Logs by resource provider
  
  
    
  
### Microsoft.AAD<a name="microsoftaaddomainservices"></a>
  
  * [Microsoft.AAD/DomainServices](Microsoft-AAD-DomainServices-logs.md)

  
### Microsoft.AgFoodPlatform<a name="microsoftagfoodplatformfarmbeats"></a>
  
  * [Microsoft.AgFoodPlatform/farmBeats](Microsoft-AgFoodPlatform-farmBeats-logs.md)

  
### Microsoft.AnalysisServices<a name="microsoftanalysisservicesservers"></a>
  
  * [Microsoft.AnalysisServices/servers](Microsoft-AnalysisServices-servers-logs.md)

  
### Microsoft.ApiManagement<a name="microsoftapimanagementservice"></a>
  
  * [Microsoft.ApiManagement/service](Microsoft-ApiManagement-service-logs.md)

  
### Microsoft.App<a name="microsoftappmanagedenvironments"></a>
  
  * [Microsoft.App/managedEnvironments](Microsoft-App-managedEnvironments-logs.md)

  
### Microsoft.AppConfiguration<a name="microsoftappconfigurationconfigurationstores"></a>
  
  * [Microsoft.AppConfiguration/configurationStores](Microsoft-AppConfiguration-configurationStores-logs.md)

  
### Microsoft.AppPlatform<a name="microsoftappplatformspring"></a>
  
  * [Microsoft.AppPlatform/Spring](Microsoft-AppPlatform-Spring-logs.md)

  
### Microsoft.Attestation<a name="microsoftattestationattestationproviders"></a>
  
  * [Microsoft.Attestation/attestationProviders](Microsoft-Attestation-attestationProviders-logs.md)

  
### Microsoft.Automation<a name="microsoftautomationautomationaccounts"></a>
  
  * [Microsoft.Automation/automationAccounts](Microsoft-Automation-automationAccounts-logs.md)

  
### Microsoft.AutonomousDevelopmentPlatform<a name="microsoftautonomousdevelopmentplatformaccounts"></a><a name="microsoftautonomousdevelopmentplatformworkspaces"></a>
  
  * [Microsoft.AutonomousDevelopmentPlatform/accounts](Microsoft-AutonomousDevelopmentPlatform-accounts-logs.md)
* [Microsoft.AutonomousDevelopmentPlatform/workspaces](Microsoft-AutonomousDevelopmentPlatform-workspaces-logs.md)

  
### microsoft.avs<a name="microsoftavsprivateclouds"></a>
  
  * [microsoft.avs/privateClouds](microsoft-avs-privateClouds-logs.md)

  
### Microsoft.AzureDataTransfer<a name="microsoftazuredatatransferconnectionsflows"></a>
  
  * [Microsoft.AzureDataTransfer/connections/flows](Microsoft-AzureDataTransfer-connections-flows-logs.md)

  
### microsoft.azureplaywrightservice<a name="microsoftazureplaywrightserviceaccounts"></a>
  
  * [microsoft.azureplaywrightservice/accounts](microsoft-azureplaywrightservice-accounts-logs.md)

  
### microsoft.azuresphere<a name="microsoftazurespherecatalogs"></a>
  
  * [microsoft.azuresphere/catalogs](microsoft-azuresphere-catalogs-logs.md)

  
### Microsoft.Batch<a name="microsoftbatchbatchaccounts"></a>
  
  * [Microsoft.Batch/batchaccounts](Microsoft-Batch-batchaccounts-logs.md)

  
### microsoft.botservice<a name="microsoftbotservicebotservices"></a>
  
  * [microsoft.botservice/botservices](microsoft-botservice-botservices-logs.md)

  
### Microsoft.Cache<a name="microsoftcacheredis"></a><a name="microsoftcacheredisenterprisedatabases"></a>
  
  * [Microsoft.Cache/redis](Microsoft-Cache-redis-logs.md)
* [Microsoft.Cache/redisEnterprise/databases](Microsoft-Cache-redisEnterprise-databases-logs.md)

  
### Microsoft.Cdn<a name="microsoftcdncdnwebapplicationfirewallpolicies"></a><a name="microsoftcdnprofiles"></a><a name="microsoftcdnprofilesendpoints"></a>
  
  * [Microsoft.Cdn/cdnwebapplicationfirewallpolicies](Microsoft-Cdn-cdnwebapplicationfirewallpolicies-logs.md)
* [Microsoft.Cdn/profiles](Microsoft-Cdn-profiles-logs.md)
* [Microsoft.Cdn/profiles/endpoints](Microsoft-Cdn-profiles-endpoints-logs.md)

  
### Microsoft.Chaos<a name="microsoftchaosexperiments"></a>
  
  * [Microsoft.Chaos/experiments](Microsoft-Chaos-experiments-logs.md)

  
### Microsoft.ClassicNetwork<a name="microsoftclassicnetworknetworksecuritygroups"></a>
  
  * [Microsoft.ClassicNetwork/networksecuritygroups](Microsoft-ClassicNetwork-networksecuritygroups-logs.md)

  
### Microsoft.Cloudtest<a name="microsoftcloudtesthostedpools"></a>
  
  * [Microsoft.Cloudtest/hostedpools](Microsoft-Cloudtest-hostedpools-logs.md)

  
### Microsoft.CodeSigning<a name="microsoftcodesigningcodesigningaccounts"></a>
  
  * [Microsoft.CodeSigning/codesigningaccounts](Microsoft-CodeSigning-codesigningaccounts-logs.md)

  
### Microsoft.CognitiveServices<a name="microsoftcognitiveservicesaccounts"></a>
  
  * [Microsoft.CognitiveServices/accounts](Microsoft-CognitiveServices-accounts-logs.md)

  
### Microsoft.Communication<a name="microsoftcommunicationcommunicationservices"></a>
  
  * [Microsoft.Communication/CommunicationServices](Microsoft-Communication-CommunicationServices-logs.md)

  
### microsoft.community<a name="microsoftcommunitycommunitytrainings"></a>
  
  * [microsoft.community/communityTrainings](microsoft-community-communityTrainings-logs.md)

  
### Microsoft.Compute<a name="microsoftcomputevirtualmachines"></a>
  
  * [Microsoft.Compute/virtualMachines](Microsoft-Compute-virtualMachines-logs.md)

  
### Microsoft.ConfidentialLedger<a name="microsoftconfidentialledgermanagedccf"></a><a name="microsoftconfidentialledgermanagedccfs"></a>
  
  * [Microsoft.ConfidentialLedger/ManagedCCF](Microsoft-ConfidentialLedger-ManagedCCF-logs.md)
* [Microsoft.ConfidentialLedger/ManagedCCFs](Microsoft-ConfidentialLedger-ManagedCCFs-logs.md)

  
### Microsoft.ConnectedCache<a name="microsoftconnectedcachecachenodes"></a><a name="microsoftconnectedcacheenterprisemcccustomers"></a><a name="microsoftconnectedcacheispcustomers"></a>
  
  * [Microsoft.ConnectedCache/CacheNodes](Microsoft-ConnectedCache-CacheNodes-logs.md)
* [Microsoft.ConnectedCache/enterpriseMccCustomers](Microsoft-ConnectedCache-enterpriseMccCustomers-logs.md)
* [Microsoft.ConnectedCache/ispCustomers](Microsoft-ConnectedCache-ispCustomers-logs.md)

  
### Microsoft.ConnectedVehicle<a name="microsoftconnectedvehicleplatformaccounts"></a>
  
  * [Microsoft.ConnectedVehicle/platformAccounts](Microsoft-ConnectedVehicle-platformAccounts-logs.md)

  
### Microsoft.ContainerInstance<a name="microsoftcontainerinstancecontainergroups"></a>
  
  * [Microsoft.ContainerInstance/containerGroups](Microsoft-ContainerInstance-containerGroups-logs.md)

  
### Microsoft.ContainerRegistry<a name="microsoftcontainerregistryregistries"></a>
  
  * [Microsoft.ContainerRegistry/registries](Microsoft-ContainerRegistry-registries-logs.md)

  
### Microsoft.ContainerService<a name="microsoftcontainerservicefleets"></a><a name="microsoftcontainerservicemanagedclusters"></a>
  
  * [Microsoft.ContainerService/fleets](Microsoft-ContainerService-fleets-logs.md)
* [Microsoft.ContainerService/managedClusters](Microsoft-ContainerService-managedClusters-logs.md)

  
### Microsoft.CustomProviders<a name="microsoftcustomprovidersresourceproviders"></a>
  
  * [Microsoft.CustomProviders/resourceproviders](Microsoft-CustomProviders-resourceproviders-logs.md)

  
### Microsoft.D365CustomerInsights<a name="microsoftd365customerinsightsinstances"></a>
  
  * [Microsoft.D365CustomerInsights/instances](Microsoft-D365CustomerInsights-instances-logs.md)

  
### Microsoft.Dashboard<a name="microsoftdashboardgrafana"></a>
  
  * [Microsoft.Dashboard/grafana](Microsoft-Dashboard-grafana-logs.md)

  
### Microsoft.Databricks<a name="microsoftdatabricksworkspaces"></a>
  
  * [Microsoft.Databricks/workspaces](Microsoft-Databricks-workspaces-logs.md)

  
### Microsoft.DataFactory<a name="microsoftdatafactoryfactories"></a>
  
  * [Microsoft.DataFactory/factories](Microsoft-DataFactory-factories-logs.md)

  
### Microsoft.DataLakeAnalytics<a name="microsoftdatalakeanalyticsaccounts"></a>
  
  * [Microsoft.DataLakeAnalytics/accounts](Microsoft-DataLakeAnalytics-accounts-logs.md)

  
### Microsoft.DataLakeStore<a name="microsoftdatalakestoreaccounts"></a>
  
  * [Microsoft.DataLakeStore/accounts](Microsoft-DataLakeStore-accounts-logs.md)

  
### Microsoft.DataProtection<a name="microsoftdataprotectionbackupvaults"></a>
  
  * [Microsoft.DataProtection/BackupVaults](Microsoft-DataProtection-BackupVaults-logs.md)

  
### Microsoft.DataShare<a name="microsoftdatashareaccounts"></a>
  
  * [Microsoft.DataShare/accounts](Microsoft-DataShare-accounts-logs.md)

  
### Microsoft.DBforMariaDB<a name="microsoftdbformariadbservers"></a>
  
  * [Microsoft.DBforMariaDB/servers](Microsoft-DBforMariaDB-servers-logs.md)

  
### Microsoft.DBforMySQL<a name="microsoftdbformysqlflexibleservers"></a><a name="microsoftdbformysqlservers"></a>
  
  * [Microsoft.DBforMySQL/flexibleServers](Microsoft-DBforMySQL-flexibleServers-logs.md)
* [Microsoft.DBforMySQL/servers](Microsoft-DBforMySQL-servers-logs.md)

  
### Microsoft.DBforPostgreSQL<a name="microsoftdbforpostgresqlflexibleservers"></a><a name="microsoftdbforpostgresqlservers"></a><a name="microsoftdbforpostgresqlserversv2"></a>
  
  * [Microsoft.DBforPostgreSQL/flexibleServers](Microsoft-DBforPostgreSQL-flexibleServers-logs.md)
* [Microsoft.DBforPostgreSQL/servers](Microsoft-DBforPostgreSQL-servers-logs.md)
* [Microsoft.DBforPostgreSQL/serversv2](Microsoft-DBforPostgreSQL-serversv2-logs.md)

  
### Microsoft.DBForPostgreSQL<a name="microsoftdbforpostgresqlservergroupsv2"></a>
  
  * [Microsoft.DBForPostgreSQL/serverGroupsv2](Microsoft-DBForPostgreSQL-serverGroupsv2-logs.md)

  
### Microsoft.DesktopVirtualization<a name="microsoftdesktopvirtualizationapplicationgroups"></a><a name="microsoftdesktopvirtualizationhostpools"></a><a name="microsoftdesktopvirtualizationscalingplans"></a><a name="microsoftdesktopvirtualizationworkspaces"></a>
  
  * [Microsoft.DesktopVirtualization/applicationgroups](Microsoft-DesktopVirtualization-applicationgroups-logs.md)
* [Microsoft.DesktopVirtualization/hostpools](Microsoft-DesktopVirtualization-hostpools-logs.md)
* [Microsoft.DesktopVirtualization/scalingplans](Microsoft-DesktopVirtualization-scalingplans-logs.md)
* [Microsoft.DesktopVirtualization/workspaces](Microsoft-DesktopVirtualization-workspaces-logs.md)

  
### Microsoft.DevCenter<a name="microsoftdevcenterdevcenters"></a>
  
  * [Microsoft.DevCenter/devcenters](Microsoft-DevCenter-devcenters-logs.md)

  
### Microsoft.Devices<a name="microsoftdevicesiothubs"></a><a name="microsoftdevicesprovisioningservices"></a>
  
  * [Microsoft.Devices/IotHubs](Microsoft-Devices-IotHubs-logs.md)
* [Microsoft.Devices/provisioningServices](Microsoft-Devices-provisioningServices-logs.md)

  
### Microsoft.DigitalTwins<a name="microsoftdigitaltwinsdigitaltwinsinstances"></a>
  
  * [Microsoft.DigitalTwins/digitalTwinsInstances](Microsoft-DigitalTwins-digitalTwinsInstances-logs.md)

  
### Microsoft.DocumentDB<a name="microsoftdocumentdbcassandraclusters"></a><a name="microsoftdocumentdbdatabaseaccounts"></a><a name="microsoftdocumentdbmongoclusters"></a>
  
  * [Microsoft.DocumentDB/cassandraClusters](Microsoft-DocumentDB-cassandraClusters-logs.md)
* [Microsoft.DocumentDB/DatabaseAccounts](Microsoft-DocumentDB-DatabaseAccounts-logs.md)
* [Microsoft.DocumentDB/mongoClusters](Microsoft-DocumentDB-mongoClusters-logs.md)

  
### Microsoft.EventGrid<a name="microsofteventgriddomains"></a><a name="microsofteventgridpartnernamespaces"></a><a name="microsofteventgridpartnertopics"></a><a name="microsofteventgridsystemtopics"></a><a name="microsofteventgridtopics"></a>
  
  * [Microsoft.EventGrid/domains](Microsoft-EventGrid-domains-logs.md)
* [Microsoft.EventGrid/partnerNamespaces](Microsoft-EventGrid-partnerNamespaces-logs.md)
* [Microsoft.EventGrid/partnerTopics](Microsoft-EventGrid-partnerTopics-logs.md)
* [Microsoft.EventGrid/systemTopics](Microsoft-EventGrid-systemTopics-logs.md)
* [Microsoft.EventGrid/topics](Microsoft-EventGrid-topics-logs.md)

  
### Microsoft.EventHub<a name="microsofteventhubnamespaces"></a>
  
  * [Microsoft.EventHub/Namespaces](Microsoft-EventHub-Namespaces-logs.md)

  
### Microsoft.HealthcareApis<a name="microsofthealthcareapisservices"></a><a name="microsofthealthcareapisworkspacesdicomservices"></a><a name="microsofthealthcareapisworkspacesfhirservices"></a><a name="microsofthealthcareapisworkspacesiotconnectors"></a>
  
  * [Microsoft.HealthcareApis/services](Microsoft-HealthcareApis-services-logs.md)
* [Microsoft.HealthcareApis/workspaces/dicomservices](Microsoft-HealthcareApis-workspaces-dicomservices-logs.md)
* [Microsoft.HealthcareApis/workspaces/fhirservices](Microsoft-HealthcareApis-workspaces-fhirservices-logs.md)
* [Microsoft.HealthcareApis/workspaces/iotconnectors](Microsoft-HealthcareApis-workspaces-iotconnectors-logs.md)

  
### microsoft.insights<a name="microsoftinsightsautoscalesettings"></a><a name="microsoftinsightscomponents"></a>
  
  * [microsoft.insights/autoscalesettings](microsoft-insights-autoscalesettings-logs.md)
* [microsoft.insights/components](microsoft-insights-components-logs.md)

  
### Microsoft.Insights<a name="microsoftinsightsdatacollectionrules"></a>
  
  * [Microsoft.Insights/datacollectionrules](Microsoft-Insights-datacollectionrules-logs.md)

  
### microsoft.keyvault<a name="microsoftkeyvaultmanagedhsms"></a>
  
  * [microsoft.keyvault/managedhsms](microsoft-keyvault-managedhsms-logs.md)

  
### Microsoft.KeyVault<a name="microsoftkeyvaultvaults"></a>
  
  * [Microsoft.KeyVault/vaults](Microsoft-KeyVault-vaults-logs.md)

  
### Microsoft.Kusto<a name="microsoftkustoclusters"></a>
  
  * [Microsoft.Kusto/clusters](Microsoft-Kusto-clusters-logs.md)

  
### microsoft.loadtestservice<a name="microsoftloadtestserviceloadtests"></a>
  
  * [microsoft.loadtestservice/loadtests](microsoft-loadtestservice-loadtests-logs.md)

  
### Microsoft.Logic<a name="microsoftlogicintegrationaccounts"></a><a name="microsoftlogicworkflows"></a>
  
  * [Microsoft.Logic/IntegrationAccounts](Microsoft-Logic-IntegrationAccounts-logs.md)
* [Microsoft.Logic/Workflows](Microsoft-Logic-Workflows-logs.md)

  
### Microsoft.MachineLearningServices<a name="microsoftmachinelearningservicesregistries"></a><a name="microsoftmachinelearningservicesworkspaces"></a><a name="microsoftmachinelearningservicesworkspacesonlineendpoints"></a>
  
  * [Microsoft.MachineLearningServices/registries](Microsoft-MachineLearningServices-registries-logs.md)
* [Microsoft.MachineLearningServices/workspaces](Microsoft-MachineLearningServices-workspaces-logs.md)
* [Microsoft.MachineLearningServices/workspaces/onlineEndpoints](Microsoft-MachineLearningServices-workspaces-onlineEndpoints-logs.md)

  
### Microsoft.ManagedNetworkFabric<a name="microsoftmanagednetworkfabricnetworkdevices"></a>
  
  * [Microsoft.ManagedNetworkFabric/networkDevices](Microsoft-ManagedNetworkFabric-networkDevices-logs.md)

  
### Microsoft.Media<a name="microsoftmediamediaservices"></a><a name="microsoftmediamediaservicesliveevents"></a><a name="microsoftmediamediaservicesstreamingendpoints"></a><a name="microsoftmediavideoanalyzers"></a>
  
  * [Microsoft.Media/mediaservices](Microsoft-Media-mediaservices-logs.md)
* [Microsoft.Media/mediaservices/liveEvents](Microsoft-Media-mediaservices-liveEvents-logs.md)
* [Microsoft.Media/mediaservices/streamingEndpoints](Microsoft-Media-mediaservices-streamingEndpoints-logs.md)
* [Microsoft.Media/videoanalyzers](Microsoft-Media-videoanalyzers-logs.md)

  
### Microsoft.NetApp<a name="microsoftnetappnetappaccountscapacitypools"></a><a name="microsoftnetappnetappaccountscapacitypoolsvolumes"></a>
  
  * [Microsoft.NetApp/netAppAccounts/capacityPools](Microsoft-NetApp-netAppAccounts-capacityPools-logs.md)
* [Microsoft.NetApp/netAppAccounts/capacityPools/volumes](Microsoft-NetApp-netAppAccounts-capacityPools-volumes-logs.md)

  
### Microsoft.Network<a name="microsoftnetworkapplicationgateways"></a><a name="microsoftnetworkazurefirewalls"></a><a name="microsoftnetworkdnsresolverpolicies"></a><a name="microsoftnetworkexpressroutecircuits"></a><a name="microsoftnetworkfrontdoors"></a><a name="microsoftnetworkloadbalancers"></a><a name="microsoftnetworknetworkmanagers"></a><a name="microsoftnetworknetworkmanagersipampools"></a><a name="microsoftnetworknetworksecuritygroups"></a><a name="microsoftnetworknetworksecurityperimeters"></a><a name="microsoftnetworknetworksecurityperimetersprofiles"></a><a name="microsoftnetworkpublicipaddresses"></a><a name="microsoftnetworkpublicipprefixes"></a><a name="microsoftnetworktrafficmanagerprofiles"></a><a name="microsoftnetworkvirtualnetworks"></a>
  
  * [Microsoft.Network/applicationgateways](Microsoft-Network-applicationgateways-logs.md)
* [Microsoft.Network/azureFirewalls](Microsoft-Network-azureFirewalls-logs.md)
* [Microsoft.Network/dnsResolverPolicies](Microsoft-Network-dnsResolverPolicies-logs.md)
* [Microsoft.Network/expressRouteCircuits](Microsoft-Network-expressRouteCircuits-logs.md)
* [Microsoft.Network/frontdoors](Microsoft-Network-frontdoors-logs.md)
* [Microsoft.Network/loadBalancers](Microsoft-Network-loadBalancers-logs.md)
* [Microsoft.Network/networkManagers](Microsoft-Network-networkManagers-logs.md)
* [Microsoft.Network/networkManagers/ipamPools](Microsoft-Network-networkManagers-ipamPools-logs.md)
* [Microsoft.Network/networksecuritygroups](Microsoft-Network-networksecuritygroups-logs.md)
* [Microsoft.Network/networkSecurityPerimeters](Microsoft-Network-networkSecurityPerimeters-logs.md)
* [Microsoft.Network/networkSecurityPerimeters/profiles](Microsoft-Network-networkSecurityPerimeters-profiles-logs.md)
* [Microsoft.Network/publicIPAddresses](Microsoft-Network-publicIPAddresses-logs.md)
* [Microsoft.Network/publicIPPrefixes](Microsoft-Network-publicIPPrefixes-logs.md)
* [Microsoft.Network/trafficManagerProfiles](Microsoft-Network-trafficManagerProfiles-logs.md)
* [Microsoft.Network/virtualNetworks](Microsoft-Network-virtualNetworks-logs.md)

  
### microsoft.network<a name="microsoftnetworkbastionhosts"></a><a name="microsoftnetworkp2svpngateways"></a><a name="microsoftnetworkvirtualnetworkgateways"></a><a name="microsoftnetworkvpngateways"></a>
  
  * [microsoft.network/bastionHosts](microsoft-network-bastionHosts-logs.md)
* [microsoft.network/p2svpngateways](microsoft-network-p2svpngateways-logs.md)
* [microsoft.network/virtualnetworkgateways](microsoft-network-virtualnetworkgateways-logs.md)
* [microsoft.network/vpngateways](microsoft-network-vpngateways-logs.md)

  
### Microsoft.NetworkAnalytics<a name="microsoftnetworkanalyticsdataproducts"></a>
  
  * [Microsoft.NetworkAnalytics/DataProducts](Microsoft-NetworkAnalytics-DataProducts-logs.md)

  
### Microsoft.NetworkCloud<a name="microsoftnetworkcloudbaremetalmachines"></a><a name="microsoftnetworkcloudclusters"></a><a name="microsoftnetworkcloudstorageappliances"></a>
  
  * [Microsoft.NetworkCloud/bareMetalMachines](Microsoft-NetworkCloud-bareMetalMachines-logs.md)
* [Microsoft.NetworkCloud/clusters](Microsoft-NetworkCloud-clusters-logs.md)
* [Microsoft.NetworkCloud/storageAppliances](Microsoft-NetworkCloud-storageAppliances-logs.md)

  
### Microsoft.NetworkFunction<a name="microsoftnetworkfunctionazuretrafficcollectors"></a>
  
  * [Microsoft.NetworkFunction/azureTrafficCollectors](Microsoft-NetworkFunction-azureTrafficCollectors-logs.md)

  
### Microsoft.NotificationHubs<a name="microsoftnotificationhubsnamespaces"></a><a name="microsoftnotificationhubsnamespacesnotificationhubs"></a>
  
  * [Microsoft.NotificationHubs/namespaces](Microsoft-NotificationHubs-namespaces-logs.md)
* [Microsoft.NotificationHubs/namespaces/notificationHubs](Microsoft-NotificationHubs-namespaces-notificationHubs-logs.md)

  
### MICROSOFT.OPENENERGYPLATFORM<a name="microsoftopenenergyplatformenergyservices"></a>
  
  * [MICROSOFT.OPENENERGYPLATFORM/ENERGYSERVICES](MICROSOFT-OPENENERGYPLATFORM-ENERGYSERVICES-logs.md)

  
### Microsoft.OpenLogisticsPlatform<a name="microsoftopenlogisticsplatformworkspaces"></a>
  
  * [Microsoft.OpenLogisticsPlatform/Workspaces](Microsoft-OpenLogisticsPlatform-Workspaces-logs.md)

  
### Microsoft.OperationalInsights<a name="microsoftoperationalinsightsworkspaces"></a>
  
  * [Microsoft.OperationalInsights/workspaces](Microsoft-OperationalInsights-workspaces-logs.md)

  
### Microsoft.PlayFab<a name="microsoftplayfabtitles"></a>
  
  * [Microsoft.PlayFab/titles](Microsoft-PlayFab-titles-logs.md)

  
### Microsoft.PowerBI<a name="microsoftpowerbitenants"></a><a name="microsoftpowerbitenantsworkspaces"></a>
  
  * [Microsoft.PowerBI/tenants](Microsoft-PowerBI-tenants-logs.md)
* [Microsoft.PowerBI/tenants/workspaces](Microsoft-PowerBI-tenants-workspaces-logs.md)

  
### Microsoft.PowerBIDedicated<a name="microsoftpowerbidedicatedcapacities"></a>
  
  * [Microsoft.PowerBIDedicated/capacities](Microsoft-PowerBIDedicated-capacities-logs.md)

  
### microsoft.purview<a name="microsoftpurviewaccounts"></a>
  
  * [microsoft.purview/accounts](microsoft-purview-accounts-logs.md)

  
### Microsoft.RecoveryServices<a name="microsoftrecoveryservicesvaults"></a>
  
  * [Microsoft.RecoveryServices/Vaults](Microsoft-RecoveryServices-Vaults-logs.md)

  
### Microsoft.Relay<a name="microsoftrelaynamespaces"></a>
  
  * [Microsoft.Relay/namespaces](Microsoft-Relay-namespaces-logs.md)

  
### Microsoft.Search<a name="microsoftsearchsearchservices"></a>
  
  * [Microsoft.Search/searchServices](Microsoft-Search-searchServices-logs.md)

  
### Microsoft.Security<a name="microsoftsecurityantimalwaresettings"></a><a name="microsoftsecuritydefenderforstoragesettings"></a>
  
  * [Microsoft.Security/antiMalwareSettings](Microsoft-Security-antiMalwareSettings-logs.md)
* [Microsoft.Security/defenderForStorageSettings](Microsoft-Security-defenderForStorageSettings-logs.md)

  
### microsoft.securityinsights<a name="microsoftsecurityinsightssettings"></a>
  
  * [microsoft.securityinsights/settings](microsoft-securityinsights-settings-logs.md)

  
### Microsoft.ServiceBus<a name="microsoftservicebusnamespaces"></a>
  
  * [Microsoft.ServiceBus/Namespaces](Microsoft-ServiceBus-Namespaces-logs.md)

  
### Microsoft.ServiceNetworking<a name="microsoftservicenetworkingtrafficcontrollers"></a>
  
  * [Microsoft.ServiceNetworking/trafficControllers](Microsoft-ServiceNetworking-trafficControllers-logs.md)

  
### Microsoft.SignalRService<a name="microsoftsignalrservicesignalr"></a><a name="microsoftsignalrservicesignalrreplicas"></a><a name="microsoftsignalrservicewebpubsub"></a><a name="microsoftsignalrservicewebpubsubreplicas"></a>
  
  * [Microsoft.SignalRService/SignalR](Microsoft-SignalRService-SignalR-logs.md)
* [Microsoft.SignalRService/SignalR/replicas](Microsoft-SignalRService-SignalR-replicas-logs.md)
* [Microsoft.SignalRService/WebPubSub](Microsoft-SignalRService-WebPubSub-logs.md)
* [Microsoft.SignalRService/WebPubSub/replicas](Microsoft-SignalRService-WebPubSub-replicas-logs.md)

  
### microsoft.singularity<a name="microsoftsingularityaccounts"></a>
  
  * [microsoft.singularity/accounts](microsoft-singularity-accounts-logs.md)

  
### Microsoft.Sql<a name="microsoftsqlmanagedinstances"></a><a name="microsoftsqlmanagedinstancesdatabases"></a><a name="microsoftsqlserversdatabases"></a>
  
  * [Microsoft.Sql/managedInstances](Microsoft-Sql-managedInstances-logs.md)
* [Microsoft.Sql/managedInstances/databases](Microsoft-Sql-managedInstances-databases-logs.md)
* [Microsoft.Sql/servers/databases](Microsoft-Sql-servers-databases-logs.md)

  
### Microsoft.Storage<a name="microsoftstoragestorageaccountsblobservices"></a><a name="microsoftstoragestorageaccountsfileservices"></a><a name="microsoftstoragestorageaccountsqueueservices"></a><a name="microsoftstoragestorageaccountstableservices"></a>
  
  * [Microsoft.Storage/storageAccounts/blobServices](Microsoft-Storage-storageAccounts-blobServices-logs.md)
* [Microsoft.Storage/storageAccounts/fileServices](Microsoft-Storage-storageAccounts-fileServices-logs.md)
* [Microsoft.Storage/storageAccounts/queueServices](Microsoft-Storage-storageAccounts-queueServices-logs.md)
* [Microsoft.Storage/storageAccounts/tableServices](Microsoft-Storage-storageAccounts-tableServices-logs.md)

  
### Microsoft.StorageCache<a name="microsoftstoragecacheamlfilesystems"></a><a name="microsoftstoragecachecaches"></a>
  
  * [Microsoft.StorageCache/amlFilesystems](Microsoft-StorageCache-amlFilesystems-logs.md)
* [Microsoft.StorageCache/caches](Microsoft-StorageCache-caches-logs.md)

  
### Microsoft.StorageMover<a name="microsoftstoragemoverstoragemovers"></a>
  
  * [Microsoft.StorageMover/storageMovers](Microsoft-StorageMover-storageMovers-logs.md)

  
### Microsoft.StreamAnalytics<a name="microsoftstreamanalyticsstreamingjobs"></a>
  
  * [Microsoft.StreamAnalytics/streamingjobs](Microsoft-StreamAnalytics-streamingjobs-logs.md)

  
### Microsoft.Synapse<a name="microsoftsynapseworkspaces"></a><a name="microsoftsynapseworkspacesbigdatapools"></a><a name="microsoftsynapseworkspaceskustopools"></a><a name="microsoftsynapseworkspacesscopepools"></a><a name="microsoftsynapseworkspacessqlpools"></a>
  
  * [Microsoft.Synapse/workspaces](Microsoft-Synapse-workspaces-logs.md)
* [Microsoft.Synapse/workspaces/bigDataPools](Microsoft-Synapse-workspaces-bigDataPools-logs.md)
* [Microsoft.Synapse/workspaces/kustoPools](Microsoft-Synapse-workspaces-kustoPools-logs.md)
* [Microsoft.Synapse/workspaces/scopePools](Microsoft-Synapse-workspaces-scopePools-logs.md)
* [Microsoft.Synapse/workspaces/sqlPools](Microsoft-Synapse-workspaces-sqlPools-logs.md)

  
### Microsoft.TimeSeriesInsights<a name="microsofttimeseriesinsightsenvironments"></a><a name="microsofttimeseriesinsightsenvironmentseventsources"></a>
  
  * [Microsoft.TimeSeriesInsights/environments](Microsoft-TimeSeriesInsights-environments-logs.md)
* [Microsoft.TimeSeriesInsights/environments/eventsources](Microsoft-TimeSeriesInsights-environments-eventsources-logs.md)

  
### microsoft.videoindexer<a name="microsoftvideoindexeraccounts"></a>
  
  * [microsoft.videoindexer/accounts](microsoft-videoindexer-accounts-logs.md)

  
### Microsoft.Web<a name="microsoftwebhostingenvironments"></a><a name="microsoftwebsites"></a><a name="microsoftwebsitesslots"></a><a name="microsoftwebstaticsites"></a>
  
  * [Microsoft.Web/hostingEnvironments](Microsoft-Web-hostingEnvironments-logs.md)
* [Microsoft.Web/sites](Microsoft-Web-sites-logs.md)
* [Microsoft.Web/sites/slots](Microsoft-Web-sites-slots-logs.md)
* [Microsoft.Web/staticsites](Microsoft-Web-staticsites-logs.md)

  
### microsoft.workloads<a name="microsoftworkloadssapvirtualinstances"></a>
  
  * [microsoft.workloads/sapvirtualinstances](microsoft-workloads-sapvirtualinstances-logs.md)

  
## Next Steps

* [Learn more about resource logs](/azure/azure-monitor/essentials/platform-logs-overview)
* [Stream resource resource logs to **Event Hubs**](/azure/azure-monitor/essentials/resource-logs#send-to-azure-event-hubs)
* [Change resource log diagnostic settings using the Azure Monitor REST API](/rest/api/monitor/diagnosticsettings)
* [Analyze logs from Azure storage with Log Analytics](/azure/azure-monitor/essentials/resource-logs#send-to-log-analytics-workspace)
