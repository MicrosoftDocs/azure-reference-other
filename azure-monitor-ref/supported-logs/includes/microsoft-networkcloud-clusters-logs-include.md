---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/01/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.NetworkCloud/clusters, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`CustomerContainerLogs` |Kubernetes Logs |[NCCKubernetesLogs](/azure/azure-monitor/reference/tables/ncckuberneteslogs)<p>Containerized application logs from Nexus clusters to gain insight onto the container orchestration platform.|Yes|No||Yes |
|`VMOrchestrationLogs` |VM Orchestration Logs |[NCCVMOrchestrationLogs](/azure/azure-monitor/reference/tables/nccvmorchestrationlogs)<p>Logs from Virtual Machine Orchestrator of Nexus cluster to track seamless coordination and management of virtual machines.|Yes|No||Yes |