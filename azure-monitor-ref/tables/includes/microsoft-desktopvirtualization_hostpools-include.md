---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.desktopvirtualization/hostpools
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|
| [WVDAgentHealthStatus](/azure/azure-monitor/reference/tables/WVDAgentHealthStatus)<p>Azure Virtual Desktop agent health status. | virtualmachines | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/wvdagenthealthstatus)|
| [WVDAutoscaleEvaluationPooled](/azure/azure-monitor/reference/tables/WVDAutoscaleEvaluationPooled)<p>The results of an Azure Virtual Desktop Autoscale scaling plan evaluation on a hostpool. This includes information on the actions Autoscale took on the sessions hosts, such as starting or deallocating them, and why it took those actions. The column names that start with 'Config' contain the scaling plan configuration values for the current Autoscale schedule phase. If the ResultType column value is 'Failed' then join to the WVDErrors table using the CorrelationId column to get more details. For Autoscale documentation see https://go.microsoft.com/fwlink/?linkid=2169532 . | windowsvirtualdesktop | LogManagement | No| -|
| [WVDCheckpoints](/azure/azure-monitor/reference/tables/WVDCheckpoints)<p>Windows Virtual Desktop Checkpoint Activity | windowsvirtualdesktop | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/wvdcheckpoints)|
| [WVDConnectionGraphicsDataPreview](/azure/azure-monitor/reference/tables/WVDConnectionGraphicsDataPreview)<p>Windows Virtual Desktop connection graphics data. | windowsvirtualdesktop | LogManagement | No| -|
| [WVDConnectionNetworkData](/azure/azure-monitor/reference/tables/WVDConnectionNetworkData)<p>Windows Virtual Desktop connection network data. | windowsvirtualdesktop | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/wvdconnectionnetworkdata)|
| [WVDConnections](/azure/azure-monitor/reference/tables/WVDConnections)<p>Windows Virtual Desktop Connection Activity. | windowsvirtualdesktop | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/wvdconnections)|
| [WVDErrors](/azure/azure-monitor/reference/tables/WVDErrors)<p>Windows Virtual Desktop Error Activity | windowsvirtualdesktop | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/wvderrors)|
| [WVDHostRegistrations](/azure/azure-monitor/reference/tables/WVDHostRegistrations)<p>Windows Virtual Desktop Host Registration Activity | windowsvirtualdesktop | LogManagement | No| -|
| [WVDManagement](/azure/azure-monitor/reference/tables/WVDManagement)<p>Windows Virtual Desktop Management Activity | windowsvirtualdesktop | LogManagement | No| -|
| [WVDSessionHostManagement](/azure/azure-monitor/reference/tables/WVDSessionHostManagement)<p>Windows Virtual Desktop session host management data. | windowsvirtualdesktop | LogManagement | No| -|

  
