---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.machinelearningservices/workspaces
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AmlComputeClusterEvent](/azure/azure-monitor/reference/tables/AmlComputeClusterEvent)<p>AmlCompute Cluster events | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/amlcomputeclusterevent)|
| [AmlComputeClusterNodeEvent](/azure/azure-monitor/reference/tables/AmlComputeClusterNodeEvent)<p>AmlCompute Cluster Node events | resources | LogManagement | No| -|
| [AmlComputeCpuGpuUtilization](/azure/azure-monitor/reference/tables/AmlComputeCpuGpuUtilization)<p>Azure Machine Learning services CPU and GPU utilizaion logs. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/amlcomputecpugpuutilization)|
| [AmlComputeInstanceEvent](/azure/azure-monitor/reference/tables/AmlComputeInstanceEvent)<p>Events when ML Compute Instance is accessed (read/write). | resources, audit | LogManagement | No| -|
| [AmlComputeJobEvent](/azure/azure-monitor/reference/tables/AmlComputeJobEvent)<p>AmlCompute Job events | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/amlcomputejobevent)|
| [AmlDataLabelEvent](/azure/azure-monitor/reference/tables/AmlDataLabelEvent)<p>Events when data label(s) or its projects is accessed (read, created, or deleted). | resources, audit | LogManagement | No| -|
| [AmlDataSetEvent](/azure/azure-monitor/reference/tables/AmlDataSetEvent)<p>Events when a registered or unregistered ML datastore is accessed (read, created, or deleted). | resources, audit | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/amldatasetevent)|
| [AmlDataStoreEvent](/azure/azure-monitor/reference/tables/AmlDataStoreEvent)<p>Events when ML datastore is accessed (read, created, or deleted). | resources, audit | LogManagement | No| -|
| [AmlDeploymentEvent](/azure/azure-monitor/reference/tables/AmlDeploymentEvent)<p>Events when a model deployment happens on ACI or AKS. | resources, audit | LogManagement | No| -|
| [AmlEnvironmentEvent](/azure/azure-monitor/reference/tables/AmlEnvironmentEvent)<p>Events when ML environments are accessed (read, created, or deleted). | resources, audit | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/amlenvironmentevent)|
| [AmlInferencingEvent](/azure/azure-monitor/reference/tables/AmlInferencingEvent)<p>Events for inference or related operation on AKS or ACI compute type. | resources, audit | LogManagement | No| -|
| [AmlModelsEvent](/azure/azure-monitor/reference/tables/AmlModelsEvent)<p>Events when ML model is accessed (read, created, or deleted). Incudes events when packaging of models and assets happen into a ready-to-build packages. | resources, audit | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/amlmodelsevent)|
| [AmlOnlineEndpointConsoleLog](/azure/azure-monitor/reference/tables/AmlOnlineEndpointConsoleLog)<p>Azure ML online endpoints console logs. It provides console logs output from user containers. | audit, resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/amlonlineendpointconsolelog)|
| [AmlOnlineEndpointEventLog](/azure/azure-monitor/reference/tables/AmlOnlineEndpointEventLog)<p>Azure ML online endpoints event logs. It provides event logs regarding the inference-server container's life cycle. | audit, resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/amlonlineendpointeventlog)|
| [AmlOnlineEndpointTrafficLog](/azure/azure-monitor/reference/tables/AmlOnlineEndpointTrafficLog)<p>Traffic logs for AzureML (machine learning) online endpoints. The table could be used to check the detailed information of the request to an online endpoint. For example, you could use it to check the request duration, the request failure reason, etc. | audit, resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/amlonlineendpointtrafficlog)|
| [AmlPipelineEvent](/azure/azure-monitor/reference/tables/AmlPipelineEvent)<p>Events when ML pipeline draft or endpoint or module are accessed (read, created, or deleted). | resources, audit | LogManagement | No| -|
| [AmlRunEvent](/azure/azure-monitor/reference/tables/AmlRunEvent)<p>Events when ML experiments are accessed (read, created, or deleted). | resources, audit | LogManagement | No| -|
| [AmlRunStatusChangedEvent](/azure/azure-monitor/reference/tables/AmlRunStatusChangedEvent)<p>Azure Machine Learning services run status event logs. | resources | LogManagement | No| -|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|

  
