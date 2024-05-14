---
ms.service: azure-monitor
ms.topic: include
ms.date: 05/13/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.eventhub/namespaces
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AZMSApplicationMetricLogs](/azure/azure-monitor/reference/tables/AZMSApplicationMetricLogs)<p>Captures application metrics(incoming/outgoing, successful/failed, etc. message delivery) for Azure Event Hubs and Azure Service Bus. | resources, audit | LogManagement | Yes| -|
| [AZMSArchiveLogs](/azure/azure-monitor/reference/tables/AZMSArchiveLogs)<p>Captures information about Event Hubs capture operations, specifically, logs related to capture errors. | resources, audit | LogManagement | Yes| -|
| [AZMSAutoscaleLogs](/azure/azure-monitor/reference/tables/AZMSAutoscaleLogs)<p>Captures auto-inflate operations done on an Event Hubs namespace. | resources, audit | LogManagement | Yes| -|
| [AZMSCustomerManagedKeyUserLogs](/azure/azure-monitor/reference/tables/AZMSCustomerManagedKeyUserLogs)<p>Captures operations related to customer-managed key. | resources, audit | LogManagement | Yes| -|
| [AZMSDiagnosticErrorLogs](/azure/azure-monitor/reference/tables/AZMSDiagnosticErrorLogs)<p>Captures aggregated diagnostic information such as client errors , server busy errors and quota exceeded errors for various data plane access operations (such as send or receive messages) in Azure Event Hubs and Azure Service Bus. | audit | LogManagement | Yes| [Yes](/azure/azure-monitor/reference/queries/azmsdiagnosticerrorlogs)|
| [AZMSKafkaCoordinatorLogs](/azure/azure-monitor/reference/tables/AZMSKafkaCoordinatorLogs)<p>Captures kafka coordinator operations related to Event Hubs. | resources, audit | LogManagement | Yes| -|
| [AZMSKafkaUserErrorLogs](/azure/azure-monitor/reference/tables/AZMSKafkaUserErrorLogs)<p>Captures information about kafka APIs called on Event Hubs. | resources, audit | LogManagement | Yes| -|
| [AZMSOperationalLogs](/azure/azure-monitor/reference/tables/AZMSOperationalLogs)<p>Captures all management operations that are performed on the Azure Event Hubs/Azure Service Bus namespace and its entities. | resources, audit | LogManagement | Yes| [Yes](/azure/azure-monitor/reference/queries/azmsoperationallogs)|
| [AZMSRunTimeAuditLogs](/azure/azure-monitor/reference/tables/AZMSRunTimeAuditLogs)<p>Captures aggregated diagnostic information for various data plane access operations (such as send or receive messages) in Azure Event Hubs and Azure Service Bus. Runtime audit logs are currently available only in premium tier. | audit | LogManagement | Yes| [Yes](/azure/azure-monitor/reference/queries/azmsruntimeauditlogs)|
| [AZMSVnetConnectionEvents](/azure/azure-monitor/reference/tables/AZMSVnetConnectionEvents)<p>Captures all virtual network and IP filtering logs for Azure Event Hubs and Azure Service Bus. These would only be emitted if namespace allows access from selected networks or from specific IP address (IP Filter rules). | resources, audit | LogManagement | Yes| [Yes](/azure/azure-monitor/reference/queries/azmsvnetconnectionevents)|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|

  
