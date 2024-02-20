---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.MachineLearningServices/workspaces, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`AmlComputeClusterEvent` |AmlComputeClusterEvent |[AmlComputeClusterEvent](/azure/azure-monitor/reference/tables/amlcomputeclusterevent)<p>AmlCompute Cluster events|No|Yes|[Queries](../../queries/amlcomputeclusterevent.md)|No |
|`AmlComputeClusterNodeEvent` |AmlComputeClusterNodeEvent ||No|Yes||Yes |
|`AmlComputeCpuGpuUtilization` |AmlComputeCpuGpuUtilization |[AmlComputeCpuGpuUtilization](/azure/azure-monitor/reference/tables/amlcomputecpugpuutilization)<p>Azure Machine Learning services CPU and GPU utilizaion logs.|No|Yes|[Queries](../../queries/amlcomputecpugpuutilization.md)|No |
|`AmlComputeJobEvent` |AmlComputeJobEvent |[AmlComputeJobEvent](/azure/azure-monitor/reference/tables/amlcomputejobevent)<p>AmlCompute Job events|No|Yes|[Queries](../../queries/amlcomputejobevent.md)|No |
|`AmlRunStatusChangedEvent` |AmlRunStatusChangedEvent |[AmlRunStatusChangedEvent](/azure/azure-monitor/reference/tables/amlrunstatuschangedevent)<p>Azure Machine Learning services run status event logs.|No|Yes||No |
|`ComputeInstanceEvent` |ComputeInstanceEvent |[AmlComputeInstanceEvent](/azure/azure-monitor/reference/tables/amlcomputeinstanceevent)<p>Events when ML Compute Instance is accessed (read/write).|No|Yes||Yes |
|`DataLabelChangeEvent` |DataLabelChangeEvent |[AmlDataLabelEvent](/azure/azure-monitor/reference/tables/amldatalabelevent)<p>Events when data label(s) or its projects is accessed (read, created, or deleted).|No|Yes||Yes |
|`DataLabelReadEvent` |DataLabelReadEvent |[AmlDataLabelEvent](/azure/azure-monitor/reference/tables/amldatalabelevent)<p>Events when data label(s) or its projects is accessed (read, created, or deleted).|No|Yes||Yes |
|`DataSetChangeEvent` |DataSetChangeEvent |[AmlDataSetEvent](/azure/azure-monitor/reference/tables/amldatasetevent)<p>Events when a registered or unregistered ML datastore is accessed (read, created, or deleted).|No|Yes|[Queries](../../queries/amldatasetevent.md)|Yes |
|`DataSetReadEvent` |DataSetReadEvent |[AmlDataSetEvent](/azure/azure-monitor/reference/tables/amldatasetevent)<p>Events when a registered or unregistered ML datastore is accessed (read, created, or deleted).|No|Yes|[Queries](../../queries/amldatasetevent.md)|Yes |
|`DataStoreChangeEvent` |DataStoreChangeEvent |[AmlDataStoreEvent](/azure/azure-monitor/reference/tables/amldatastoreevent)<p>Events when ML datastore is accessed (read, created, or deleted).|No|Yes||Yes |
|`DataStoreReadEvent` |DataStoreReadEvent |[AmlDataStoreEvent](/azure/azure-monitor/reference/tables/amldatastoreevent)<p>Events when ML datastore is accessed (read, created, or deleted).|No|Yes||Yes |
|`DeploymentEventACI` |DeploymentEventACI |[AmlDeploymentEvent](/azure/azure-monitor/reference/tables/amldeploymentevent)<p>Events when a model deployment happens on ACI or AKS.|No|Yes||Yes |
|`DeploymentEventAKS` |DeploymentEventAKS |[AmlDeploymentEvent](/azure/azure-monitor/reference/tables/amldeploymentevent)<p>Events when a model deployment happens on ACI or AKS.|No|Yes||Yes |
|`DeploymentReadEvent` |DeploymentReadEvent |[AmlDeploymentEvent](/azure/azure-monitor/reference/tables/amldeploymentevent)<p>Events when a model deployment happens on ACI or AKS.|No|Yes||Yes |
|`EnvironmentChangeEvent` |EnvironmentChangeEvent |[AmlEnvironmentEvent](/azure/azure-monitor/reference/tables/amlenvironmentevent)<p>Events when ML environments are accessed (read, created, or deleted).|No|Yes|[Queries](../../queries/amlenvironmentevent.md)|Yes |
|`EnvironmentReadEvent` |EnvironmentReadEvent |[AmlEnvironmentEvent](/azure/azure-monitor/reference/tables/amlenvironmentevent)<p>Events when ML environments are accessed (read, created, or deleted).|No|Yes|[Queries](../../queries/amlenvironmentevent.md)|Yes |
|`InferencingOperationACI` |InferencingOperationACI |[AmlInferencingEvent](/azure/azure-monitor/reference/tables/amlinferencingevent)<p>Events for inference or related operation on AKS or ACI compute type.|No|Yes||Yes |
|`InferencingOperationAKS` |InferencingOperationAKS |[AmlInferencingEvent](/azure/azure-monitor/reference/tables/amlinferencingevent)<p>Events for inference or related operation on AKS or ACI compute type.|No|Yes||Yes |
|`ModelsActionEvent` |ModelsActionEvent |[AmlModelsEvent](/azure/azure-monitor/reference/tables/amlmodelsevent)<p>Events when ML model is accessed (read, created, or deleted). Incudes events when packaging of models and assets happen into a ready-to-build packages.|No|Yes|[Queries](../../queries/amlmodelsevent.md)|Yes |
|`ModelsChangeEvent` |ModelsChangeEvent |[AmlModelsEvent](/azure/azure-monitor/reference/tables/amlmodelsevent)<p>Events when ML model is accessed (read, created, or deleted). Incudes events when packaging of models and assets happen into a ready-to-build packages.|No|Yes|[Queries](../../queries/amlmodelsevent.md)|Yes |
|`ModelsReadEvent` |ModelsReadEvent |[AmlModelsEvent](/azure/azure-monitor/reference/tables/amlmodelsevent)<p>Events when ML model is accessed (read, created, or deleted). Incudes events when packaging of models and assets happen into a ready-to-build packages.|No|Yes|[Queries](../../queries/amlmodelsevent.md)|Yes |
|`PipelineChangeEvent` |PipelineChangeEvent |[AmlPipelineEvent](/azure/azure-monitor/reference/tables/amlpipelineevent)<p>Events when ML pipeline draft or endpoint or module are accessed (read, created, or deleted).|No|Yes||Yes |
|`PipelineReadEvent` |PipelineReadEvent |[AmlPipelineEvent](/azure/azure-monitor/reference/tables/amlpipelineevent)<p>Events when ML pipeline draft or endpoint or module are accessed (read, created, or deleted).|No|Yes||Yes |
|`RunEvent` |RunEvent |[AmlRunEvent](/azure/azure-monitor/reference/tables/amlrunevent)<p>Events when ML experiments are accessed (read, created, or deleted).|No|Yes||Yes |
|`RunReadEvent` |RunReadEvent |[AmlRunEvent](/azure/azure-monitor/reference/tables/amlrunevent)<p>Events when ML experiments are accessed (read, created, or deleted).|No|Yes||Yes |