---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/22/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.apimanagement/service
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [APIMDevPortalAuditDiagnosticLog](/azure/azure-monitor/reference/tables/APIMDevPortalAuditDiagnosticLog)<p>Diagnostic Logs for API Management Developer Portal API. |  | LogManagement | No| -|
| [ApiManagementGatewayLogs](/azure/azure-monitor/reference/tables/ApiManagementGatewayLogs)<p>Azure ApiManagement gateway logs. | resources | LogManagement | Yes| [Yes](/azure/azure-monitor/reference/queries/apimanagementgatewaylogs)|
| [ApiManagementWebSocketConnectionLogs](/azure/azure-monitor/reference/tables/ApiManagementWebSocketConnectionLogs)<p>Websocket connection logs provides logs on websocket connection events for API Management Gateway. Logging starts when the request arrives to API Management Gateway for handshake and till the request gets terminated. Every request log can be uniquely identified with CorrelationId. | resources | LogManagement | Yes| -|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|

  
