---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.machinelearningservices/registries
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AmlRegistryReadEventsLog](/azure/azure-monitor/reference/tables/AmlRegistryReadEventsLog)<p>Azure ML Registry Read events log. It keeps records of Read operations with registries data access (data plane), including user identity, asset name and version for each access event. | audit, resources | LogManagement | No| -|
| [AmlRegistryWriteEventsLog](/azure/azure-monitor/reference/tables/AmlRegistryWriteEventsLog)<p>Azure ML Registry Write events log. It keeps records of Write operations with registries data access (data plane), including user identity, asset name and version for each access event. | audit, resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/amlregistrywriteeventslog)|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|

  
