---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Relay/namespaces, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`HybridConnectionsEvent` |HybridConnections Events |[AZMSHybridConnectionsEvents](/azure/azure-monitor/reference/tables/azmshybridconnectionsevents)<p>Captures all hybrid connection events that are performed on the Azure Relay namespace.|Yes|No|[Queries](../../queries/azmshybridconnectionsevents.md)|No |
|`VNetAndIPFilteringLogs` |VNet/IP Filtering Connection Logs |[AzureDiagnostics](/azure/azure-monitor/reference/tables/azurediagnostics)<p>Diagnostic logs emitted by Azure services describe the operation of those services or resources. All diagnostic logs share a common top-level schema, which services extend to emit unique properties for their specifc events. Note: many services are now ingesting their diagnostic logs into resource-specific tables, see more here|No|No||Yes |