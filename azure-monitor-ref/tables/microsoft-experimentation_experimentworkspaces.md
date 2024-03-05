---
title: Azure Monitor tables for microsoft.experimentation/experimentworkspaces
description: Azure Monitor tables for resource type microsoft.experimentation/experimentworkspaces
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
   
ms.date: 03/05/2024


---

# Resource log tables for microsoft.experimentation/experimentworkspaces  


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AEWAssignmentBlobLogs](/azure/azure-monitor/reference/tables/AEWAssignmentBlobLogs)<p>Assignment blob upload events for the Experiment Workspace. | resources, audit | LogManagement | No| -|
| [AEWAuditLogs](/azure/azure-monitor/reference/tables/AEWAuditLogs)<p>Audit, activity and status for the Experiment Workspace. | resources, audit | LogManagement | No| -|
| [AEWComputePipelinesLogs](/azure/azure-monitor/reference/tables/AEWComputePipelinesLogs)<p>AEWComputePipelines Events for the Experiment Workspace. | resources, audit | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/aewcomputepipelineslogs)|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|

