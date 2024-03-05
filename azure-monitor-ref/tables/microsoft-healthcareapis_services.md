---
title: Azure Monitor tables for microsoft.healthcareapis/services
description: Azure Monitor tables for resource type microsoft.healthcareapis/services
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
   
ms.date: 03/05/2024


---

# Resource log tables for microsoft.healthcareapis/services  


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|
| [MicrosoftHealthcareApisAuditLogs](/azure/azure-monitor/reference/tables/MicrosoftHealthcareApisAuditLogs)<p>Azure API for FHIR audit logs | resources, audit | LogManagement | No| -|

