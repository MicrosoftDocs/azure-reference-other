---
title: Azure Monitor Logs reference - AzureMetrics
description: Reference for AzureMetrics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# AzureMetrics

Metric data emitted by Azure services that measure their health and performance.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.aad/domainservices,<br>microsoft.network/applicationgateways,<br>microsoft.servicenetworking/trafficcontrollers,<br>microsoft.web/sites,<br>microsoft.kubernetes/connectedclusters,<br>microsoft.cache/redis,<br>microsoft.hardwaresecuritymodules/cloudhsmclusters,<br>microsoft.communication/communicationservices,<br>microsoft.documentdb/databaseaccounts,<br>microsoft.datacollaboration/workspaces,<br>microsoft.eventgrid/namespaces,<br>microsoft.eventgrid/topics,<br>microsoft.eventhub/namespaces,<br>microsoft.network/azurefirewalls,<br>microsoft.keyvault/vaults,<br>microsoft.containerservice/managedclusters,<br>microsoft.managednetworkfabric/networkdevices,<br>microsoft.networkcloud/baremetalmachines,<br>microsoft.networkcloud/clusters,<br>microsoft.networkcloud/storageappliances,<br>microsoft.relay/namespaces,<br>microsoft.servicebus/namespaces,<br>microsoft.networkfunction/azuretrafficcollectors,<br>microsoft.network/networkmanagers,<br>microsoft.cognitiveservices/accounts,<br>microsoft.connectedcache/cachenodes,<br>microsoft.connectedvehicle/platformaccounts,<br>microsoft.databricks/workspaces,<br>microsoft.dbformysql/flexibleservers,<br>microsoft.dbforpostgresql/flexibleservers,<br>microsoft.dbforpostgresql/servergroupsv2,<br>microsoft.devcenter/devcenters,<br>microsoft.compute/virtualmachines,<br>microsoft.machinelearningservices/workspaces,<br>microsoft.media/mediaservices,<br>microsoft.azureplaywrightservice/accounts,<br>microsoft.networkanalytics/dataproducts,<br>microsoft.storage/storageaccounts,<br>microsoft.storagecache/amlfilesytems,<br>microsoft.storagemover/storagemovers,<br>microsoft.synapse/workspaces,<br>microsoft.desktopvirtualization/hostpools,<br>microsoft.desktopvirtualization/applicationgroups,<br>microsoft.desktopvirtualization/workspaces,<br>microsoft.timeseriesinsights/environments,<br>microsoft.workloadmonitor/monitors,<br>microsoft.analysisservices/servers,<br>microsoft.batch/batchaccounts,<br>microsoft.appplatform/spring,<br>microsoft.signalrservice/signalr,<br>microsoft.containerregistry/registries,<br>microsoft.kusto/clusters,<br>microsoft.blockchain/blockchainmembers,<br>microsoft.eventgrid/domains,<br>microsoft.eventgrid/partnernamespaces,<br>microsoft.eventgrid/partnertopics,<br>microsoft.eventgrid/systemtopics,<br>microsoft.conenctedvmwarevsphere/virtualmachines,<br>microsoft.azurestackhci/virtualmachines,<br>microsoft.scvmm/virtualmachines,<br>microsoft.compute/virtualmachinescalesets,<br>microsoft.hybridcontainerservice/provisionedclusters,<br>microsoft.insights/autoscalesettings,<br>microsoft.devices/iothubs,<br>microsoft.servicefabric/clusters,<br>microsoft.logic/workflows,<br>microsoft.apimanagement/service,<br>microsoft.automation/automationaccounts,<br>microsoft.datafactory/factories,<br>microsoft.datalakestore/accounts,<br>microsoft.datalakeanalytics/accounts,<br>microsoft.powerbidedicated/capacities,<br>microsoft.datashare/accounts,<br>microsoft.sql/managedinstances,<br>microsoft.sql/servers,<br>microsoft.sql/servers/databases,<br>microsoft.dbformysql/servers,<br>microsoft.dbforpostgresql/servers,<br>microsoft.dbforpostgresql/serversv2,<br>microsoft.dbformariadb/servers,<br>microsoft.devices/provisioningservices,<br>microsoft.network/expressroutecircuits,<br>microsoft.network/frontdoors,<br>microsoft.network/networkinterfaces,<br>microsoft.network/networksecuritygroups,<br>microsoft.network/publicipaddresses,<br>microsoft.network/trafficmanagerprofiles,<br>microsoft.network/virtualnetworkgateways,<br>microsoft.network/vpngateways,<br>microsoft.network/virtualnetworks,<br>microsoft.search/searchservices,<br>microsoft.streamanalytics/streamingjobs,<br>microsoft.network/bastionhosts,<br>microsoft.healthcareapis/services|
|**Categories**|Azure Resources|
|**Solutions**| LogManagement|
|**Basic log**|No|
|**Ingestion-time transformation**|No|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/azuremetrics)|



## Columns
  
[!INCLUDE [azuremetrics](.././tables/includes/azuremetrics-include.md)]
