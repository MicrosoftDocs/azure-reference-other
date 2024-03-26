---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.experimentation/experimentworkspaces
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AEWAssignmentBlobLogs](/azure/azure-monitor/reference/tables/AEWAssignmentBlobLogs)<p>Assignment blob upload events for the Experiment Workspace. | resources, audit | LogManagement | No| -|
| [AEWAuditLogs](/azure/azure-monitor/reference/tables/AEWAuditLogs)<p>Audit, activity and status for the Experiment Workspace. | resources, audit | LogManagement | No| -|
| [AEWComputePipelinesLogs](/azure/azure-monitor/reference/tables/AEWComputePipelinesLogs)<p>AEWComputePipelines Events for the Experiment Workspace. | resources, audit | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/aewcomputepipelineslogs)|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|

  
