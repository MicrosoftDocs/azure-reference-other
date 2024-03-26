---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.loadtestservice/loadtests
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureLoadTestingOperation](/azure/azure-monitor/reference/tables/AzureLoadTestingOperation)<p>Details about the operations which are performed on the Azure Load Testing resource. For example, operations like creation of a Test, Test run etc. | resources, audit | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureloadtestingoperation)|

  
