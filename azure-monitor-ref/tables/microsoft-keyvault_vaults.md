---
title: Azure Monitor tables for microsoft.keyvault/vaults
description: Azure Monitor tables for resource type microsoft.keyvault/vaults
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
   
ms.date: 03/05/2024


---

# Resource log tables for microsoft.keyvault/vaults  


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AZKVAuditLogs](/azure/azure-monitor/reference/tables/AZKVAuditLogs)<p>Audit logs can be used to monitor how and when your key vaults are accessed, and by whom. Customers will be able to log all authentication api requests. Operations on the key vault itself, including creation, deletion, setting key vault access policies, and updating key vault attributes such as tags.Operation on keys and secrets in keyvault including creating, deleting, signing. | resources, audit | LogManagement | Yes| [Yes](/azure/azure-monitor/reference/queries/azkvauditlogs)|
| [AZKVPolicyEvaluationDetailsLogs](/azure/azure-monitor/reference/tables/AZKVPolicyEvaluationDetailsLogs)<p>Contains details of Azure Policy Evaluation including the outcome and details of what checks were performed. | resources, audit | LogManagement | Yes| -|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|

