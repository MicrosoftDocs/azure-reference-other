---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.hardwaresecuritymodules/cloudhsmclusters
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|
| [CHSMManagementAuditLogs](/azure/azure-monitor/reference/tables/CHSMManagementAuditLogs)<p>This table contains audit logs retrieved from your Azure CloudHsm resource's HSM partitions. These logs captures all management operations performed by Customer over E2E channel on each HSM partition of that CloudHsm resource. They can be used to monitor events and configure necessary alerts on your CloudHsm resource. | resources, audit | LogManagement | Yes| [Yes](/azure/azure-monitor/reference/queries/chsmmanagementauditlogs)|

  
