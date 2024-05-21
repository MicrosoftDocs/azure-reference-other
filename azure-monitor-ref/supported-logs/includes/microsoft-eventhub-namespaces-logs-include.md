---
ms.service: azure-monitor
ms.topic: include
ms.date: 05/20/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.EventHub/Namespaces, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`ApplicationMetricsLogs` |Application Metrics Logs |[AZMSApplicationMetricLogs](/azure/azure-monitor/reference/tables/azmsapplicationmetriclogs)<p>Captures application metrics(incoming/outgoing, successful/failed, etc. message delivery) for Azure Event Hubs and Azure Service Bus.|Yes|No||Yes |
|`ArchiveLogs` |Archive Logs |[AZMSArchiveLogs](/azure/azure-monitor/reference/tables/azmsarchivelogs)<p>Captures information about Event Hubs capture operations, specifically, logs related to capture errors.|Yes|No||No |
|`AutoScaleLogs` |Auto Scale Logs |[AZMSAutoscaleLogs](/azure/azure-monitor/reference/tables/azmsautoscalelogs)<p>Captures auto-inflate operations done on an Event Hubs namespace.|Yes|No||No |
|`CustomerManagedKeyUserLogs` |Customer Managed Key Logs ||No|No||No |
|`DataDRLogs` |DataDR Logs ||No|No||Yes |
|`DiagnosticErrorLogs` |Diagnostic Error Logs |[AZMSDiagnosticErrorLogs](/azure/azure-monitor/reference/tables/azmsdiagnosticerrorlogs)<p>Captures aggregated diagnostic information such as client errors , server busy errors and quota exceeded errors for various data plane access operations (such as send or receive messages) in Azure Event Hubs and Azure Service Bus.|Yes|No|[Queries](/azure/azure-monitor/reference/queries/azmsdiagnosticerrorlogs)|Yes |
|`EventHubVNetConnectionEvent` |VNet/IP Filtering Connection Logs |[AZMSVnetConnectionEvents](/azure/azure-monitor/reference/tables/azmsvnetconnectionevents)<p>Captures all virtual network and IP filtering logs for Azure Event Hubs and Azure Service Bus. These would only be emitted if namespace allows access from selected networks or from specific IP address (IP Filter rules).|Yes|No|[Queries](/azure/azure-monitor/reference/queries/azmsvnetconnectionevents)|No |
|`KafkaCoordinatorLogs` |Kafka Coordinator Logs |[AZMSKafkaCoordinatorLogs](/azure/azure-monitor/reference/tables/azmskafkacoordinatorlogs)<p>Captures kafka coordinator operations related to Event Hubs.|Yes|No||No |
|`KafkaUserErrorLogs` |Kafka User Error Logs |[AZMSKafkaUserErrorLogs](/azure/azure-monitor/reference/tables/azmskafkausererrorlogs)<p>Captures information about kafka APIs called on Event Hubs.|Yes|No||No |
|`OperationalLogs` |Operational Logs |[AZMSOperationalLogs](/azure/azure-monitor/reference/tables/azmsoperationallogs)<p>Captures all management operations that are performed on the Azure Event Hubs/Azure Service Bus namespace and its entities.|Yes|No|[Queries](/azure/azure-monitor/reference/queries/azmsoperationallogs)|No |
|`RuntimeAuditLogs` |Runtime Audit Logs |[AZMSRunTimeAuditLogs](/azure/azure-monitor/reference/tables/azmsruntimeauditlogs)<p>Captures aggregated diagnostic information for various data plane access operations (such as send or receive messages) in Azure Event Hubs and Azure Service Bus. Runtime audit logs are currently available only in premium tier.|Yes|No|[Queries](/azure/azure-monitor/reference/queries/azmsruntimeauditlogs)|Yes |