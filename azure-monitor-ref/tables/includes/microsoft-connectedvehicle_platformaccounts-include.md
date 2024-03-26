---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.connectedvehicle/platformaccounts
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|
| [MCVPAuditLogs](/azure/azure-monitor/reference/tables/MCVPAuditLogs)<p>The MCVP audit logs. This table will include audit logs for MCVP service transactions. | resources | LogManagement | No| -|
| [MCVPOperationLogs](/azure/azure-monitor/reference/tables/MCVPOperationLogs)<p>The MCVP Azure monitor logs. This table will include logs for vehicle provision, connection and activities sending command and receiving telemetry messages. | resources | LogManagement | No| -|

  
