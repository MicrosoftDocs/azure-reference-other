---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.digitaltwins/digitaltwinsinstances
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [ADTDataHistoryOperation](/azure/azure-monitor/reference/tables/ADTDataHistoryOperation)<p>This table tracks all data history events being published to time series database connections. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/adtdatahistoryoperation)|
| [ADTDigitalTwinsOperation](/azure/azure-monitor/reference/tables/ADTDigitalTwinsOperation)<p>Schema for Azure Digital Twins' Digital Twin operations. The Digital Twins Operation category tracks all customer requests to manage a digital twin, including CRUD on Twins and Relationships. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/adtdigitaltwinsoperation)|
| [ADTEventRoutesOperation](/azure/azure-monitor/reference/tables/ADTEventRoutesOperation)<p>Schema for Azure Digital Twins' Event Routes operations. The Event Routes Operation category tracks all events being published to endpoints, which are other Azure services. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/adteventroutesoperation)|
| [ADTModelsOperation](/azure/azure-monitor/reference/tables/ADTModelsOperation)<p>Schema for Azure Digital Twins' Models operations. The Models Operation category tracks all customer requests to manage models in a digital twins instance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/adtmodelsoperation)|
| [ADTQueryOperation](/azure/azure-monitor/reference/tables/ADTQueryOperation)<p>Schema for Azure Digital Twins' Query operations. The Query Operation category tracks all customer requests to query their digital twins instance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/adtqueryoperation)|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|

  
