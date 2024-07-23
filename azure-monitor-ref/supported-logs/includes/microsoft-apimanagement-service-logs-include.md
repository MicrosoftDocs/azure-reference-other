---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/23/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.ApiManagement/service, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`DeveloperPortalAuditLogs` |Logs related to Developer Portal usage |[APIMDevPortalAuditDiagnosticLog](/azure/azure-monitor/reference/tables/apimdevportalauditdiagnosticlog)<p>Diagnostic Logs for API Management Developer Portal API.|Yes|No||Yes |
|`GatewayLogs` |Logs related to ApiManagement Gateway |[ApiManagementGatewayLogs](/azure/azure-monitor/reference/tables/apimanagementgatewaylogs)<p>Azure ApiManagement gateway logs.|Yes|Yes|[Queries](/azure/azure-monitor/reference/queries/apimanagementgatewaylogs)|No |
|`WebSocketConnectionLogs` |Logs related to Websocket Connections |[ApiManagementWebSocketConnectionLogs](/azure/azure-monitor/reference/tables/apimanagementwebsocketconnectionlogs)<p>Websocket connection logs provides logs on websocket connection events for API Management Gateway. Logging starts when the request arrives to API Management Gateway for handshake and till the request gets terminated. Every request log can be uniquely identified with CorrelationId.|Yes|No||Yes |