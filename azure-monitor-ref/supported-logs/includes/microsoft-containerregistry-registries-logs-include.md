---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/02/2024
ms.author: orens
author: osalzberg
ms.custom: Microsoft.ContainerRegistry/registries, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`ContainerRegistryLoginEvents` |Login Events |[ContainerRegistryLoginEvents](/azure/azure-monitor/reference/tables/containerregistryloginevents)<p>Azure Container Registry Login Auditing Logs|No|Yes|[Queries](/azure/azure-monitor/reference/queries/containerregistryloginevents)|No |
|`ContainerRegistryRepositoryEvents` |RepositoryEvent logs |[ContainerRegistryRepositoryEvents](/azure/azure-monitor/reference/tables/containerregistryrepositoryevents)<p>Azure Container Registry Repository Auditing Logs|No|Yes|[Queries](/azure/azure-monitor/reference/queries/containerregistryrepositoryevents)|No |