---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.managednetworkfabric/networkdevices
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|
| [MNFDeviceUpdates](/azure/azure-monitor/reference/tables/MNFDeviceUpdates)<p>Components state updates representing the status changes of ethernet ports, power supply units, fan modules, chassis and device software. | network | LogManagement | Yes| [Yes](/azure/azure-monitor/reference/queries/mnfdeviceupdates)|
| [MNFSystemSessionHistoryUpdates](/azure/azure-monitor/reference/tables/MNFSystemSessionHistoryUpdates)<p>System session history update events in the Nexus network fabric devices. | network | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/mnfsystemsessionhistoryupdates)|
| [MNFSystemStateMessageUpdates](/azure/azure-monitor/reference/tables/MNFSystemStateMessageUpdates)<p>System state message update events in the Nexus network fabric devices. | network | LogManagement | Yes| [Yes](/azure/azure-monitor/reference/queries/mnfsystemstatemessageupdates)|

  
