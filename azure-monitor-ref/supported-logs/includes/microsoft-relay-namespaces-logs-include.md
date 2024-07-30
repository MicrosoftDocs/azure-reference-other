---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: Microsoft.Relay/namespaces, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`HybridConnectionsEvent` |HybridConnections Events |[AZMSHybridConnectionsEvents](/azure/azure-monitor/reference/tables/azmshybridconnectionsevents)<p>Captures all hybrid connection events that are performed on the Azure Relay namespace.|Yes|No|[Queries](/azure/azure-monitor/reference/queries/azmshybridconnectionsevents)|No |
|`VNetAndIPFilteringLogs` |VNet/IP Filtering Connection Logs |[AZMSVnetConnectionEvents](/azure/azure-monitor/reference/tables/azmsvnetconnectionevents)<p>Captures all virtual network and IP filtering logs for Azure Event Hubs and Azure Service Bus. These would only be emitted if namespace allows access from selected networks or from specific IP address (IP Filter rules).|Yes|No|[Queries](/azure/azure-monitor/reference/queries/azmsvnetconnectionevents)|Yes |