---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/23/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.ContainerInstance/containerGroups, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`ContainerEvent` |Container events |[ContainerEvent](/azure/azure-monitor/reference/tables/containerevent)<p>Container Event Customer Logs.|No|No||Yes |
|`ContainerInstanceLog` |Standard output logs |[ContainerInstanceLog](/azure/azure-monitor/reference/tables/containerinstancelog)<p>Container Instance Customer Logs.|No|No||Yes |