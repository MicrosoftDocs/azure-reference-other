---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.ServiceBus/Namespaces, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`ApplicationMetricsLogs` |Application Metrics Logs(Unused) |[AZMSApplicationMetricLogs](/azure/azure-monitor/reference/tables/azmsapplicationmetriclogs)<p>Captures application metrics(incoming/outgoing, successful/failed, etc. message delivery) for Azure Event Hubs and Azure Service Bus.|Yes|No||Yes |
|`DiagnosticErrorLogs` |Diagnostic Error Logs |[AzureDiagnostics](/azure/azure-monitor/reference/tables/azurediagnostics)<p>Diagnostic logs emitted by Azure services describe the operation of those services or resources. All diagnostic logs share a common top-level schema, which services extend to emit unique properties for their specifc events. Note: many services are now ingesting their diagnostic logs into resource-specific tables, see more here|No|No|[Queries](../../queries/azurediagnostics.md#queries-for-microsoftservicebus)|Yes |
|`OperationalLogs` |Operational Logs |[AZMSOperationalLogs](/azure/azure-monitor/reference/tables/azmsoperationallogs)<p>Captures all management operations that are performed on the Azure Event Hubs/Azure Service Bus namespace and its entities.|Yes|No|[Queries](../../queries/azmsoperationallogs.md)|No |
|`RuntimeAuditLogs` |Runtime Audit Logs |[AZMSRunTimeAuditLogs](/azure/azure-monitor/reference/tables/azmsruntimeauditlogs)<p>Captures aggregated diagnostic information for various data plane access operations (such as send or receive messages) in Azure Event Hubs and Azure Service Bus. Runtime audit logs are currently available only in premium tier.|Yes|No|[Queries](../../queries/azmsruntimeauditlogs.md)|Yes |
|`VNetAndIPFilteringLogs` |VNet/IP Filtering Connection Logs |[AZMSVnetConnectionEvents](/azure/azure-monitor/reference/tables/azmsvnetconnectionevents)<p>Captures all virtual network and IP filtering logs for Azure Event Hubs and Azure Service Bus. These would only be emitted if namespace allows access from selected networks or from specific IP address (IP Filter rules).|Yes|No|[Queries](../../queries/azmsvnetconnectionevents.md)|No |