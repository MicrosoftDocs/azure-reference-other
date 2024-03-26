---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.autonomousdevelopmentplatform/workspaces
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [ADPAudit](/azure/azure-monitor/reference/tables/ADPAudit)<p>Audit entries for ADP operations. | resources, audit | LogManagement | No| -|
| [ADPDiagnostics](/azure/azure-monitor/reference/tables/ADPDiagnostics)<p>Diagnostic logs of the ADP service. | resources | LogManagement | No| -|
| [ADPRequests](/azure/azure-monitor/reference/tables/ADPRequests)<p>Requests made to the ADP service. | resources | LogManagement | No| -|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|

  
