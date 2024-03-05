---
title: Azure Monitor tables for microsoft.chaos/experiments
description: Azure Monitor tables for resource type microsoft.chaos/experiments
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
   
ms.date: 03/05/2024


---

# Resource log tables for microsoft.chaos/experiments  


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [ChaosStudioExperimentEventLogs](/azure/azure-monitor/reference/tables/ChaosStudioExperimentEventLogs)<p>Chao Studio Experiment Orchestration events. Displays Start/Stop events of each Step/Branch/Action in experiment runs. | resources, audit | LogManagement | Yes| [Yes](/azure/azure-monitor/reference/queries/chaosstudioexperimenteventlogs)|

