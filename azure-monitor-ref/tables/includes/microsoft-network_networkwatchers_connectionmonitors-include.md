---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.network/networkwatchers/connectionmonitors
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [NWConnectionMonitorDNSResult](/azure/azure-monitor/reference/tables/NWConnectionMonitorDNSResult)<p>Connection Monitor DNS result records. | network | LogManagement | No| -|
| [NWConnectionMonitorPathResult](/azure/azure-monitor/reference/tables/NWConnectionMonitorPathResult)<p>Connection Monitor path result records. | network | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/nwconnectionmonitorpathresult)|
| [NWConnectionMonitorTestResult](/azure/azure-monitor/reference/tables/NWConnectionMonitorTestResult)<p>Connection Monitor test result records. | network | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/nwconnectionmonitortestresult)|

  
