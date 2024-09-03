---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/02/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.eventgrid/namespaces
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|
| [EGNFailedHttpDataPlaneOperations](/azure/azure-monitor/reference/tables/EGNFailedHttpDataPlaneOperations)<p>Log for failed HTTP data plane requests to an Event Grid namespace. It can be used for auditing purposes. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/egnfailedhttpdataplaneoperations)|
| [EGNFailedMqttConnections](/azure/azure-monitor/reference/tables/EGNFailedMqttConnections)<p>Log for failed MQTT connections to an Event Grid namespace. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/egnfailedmqttconnections)|
| [EGNFailedMqttPublishedMessages](/azure/azure-monitor/reference/tables/EGNFailedMqttPublishedMessages)<p>Log for failed MQTT published messages to an Event Grid namespace. | resources | LogManagement | No| -|
| [EGNFailedMqttSubscriptions](/azure/azure-monitor/reference/tables/EGNFailedMqttSubscriptions)<p>Log for failed MQTT subscriptions to an Event Grid namespace. | resources | LogManagement | No| -|
| [EGNMqttDisconnections](/azure/azure-monitor/reference/tables/EGNMqttDisconnections)<p>Log for disconnected MQTT connections from an Event Grid namespace. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/egnmqttdisconnections)|
| [EGNSuccessfulHttpDataPlaneOperations](/azure/azure-monitor/reference/tables/EGNSuccessfulHttpDataPlaneOperations)<p>Log for successful HTTP data plane requests to an Event Grid namespace. It can be used for auditing purposes. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/egnsuccessfulhttpdataplaneoperations)|
| [EGNSuccessfulMqttConnections](/azure/azure-monitor/reference/tables/EGNSuccessfulMqttConnections)<p>Log for successful MQTT connections to an Event Grid namesapce. This log can be used for auditing purposes. | resources, audit | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/egnsuccessfulmqttconnections)|

  
