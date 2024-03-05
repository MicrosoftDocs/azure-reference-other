---
title: Azure Monitor tables for microsoft.devcenter/devcenters
description: Azure Monitor tables for resource type microsoft.devcenter/devcenters
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
   
ms.date: 03/05/2024


---

# Resource log tables for microsoft.devcenter/devcenters  


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|
| [DevCenterBillingEventLogs](/azure/azure-monitor/reference/tables/DevCenterBillingEventLogs)<p>Billing event related to DevCenter resources. Logs contains information about the quantity and unit charged per meter. | resources | LogManagement | Yes| -|
| [DevCenterDiagnosticLogs](/azure/azure-monitor/reference/tables/DevCenterDiagnosticLogs)<p>Data plane audit logs related to your dev center resources. Will display information concerning stop/start/deletes on dev boxes and environments. | audit, resources | LogManagement | Yes| [Yes](/azure/azure-monitor/reference/queries/devcenterdiagnosticlogs)|
| [DevCenterResourceOperationLogs](/azure/azure-monitor/reference/tables/DevCenterResourceOperationLogs)<p>Operation logs pertaining to DevCenter resources, including information around resource health status changes. | resources | LogManagement | Yes| [Yes](/azure/azure-monitor/reference/queries/devcenterresourceoperationlogs)|

