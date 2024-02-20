---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Network/expressRouteCircuits, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`PeeringRouteLog` |Peering Route Table Logs |[AzureDiagnostics](/azure/azure-monitor/reference/tables/azurediagnostics)<p>Diagnostic logs emitted by Azure services describe the operation of those services or resources. All diagnostic logs share a common top-level schema, which services extend to emit unique properties for their specifc events. Note: many services are now ingesting their diagnostic logs into resource-specific tables, see more here|No|No|[Queries](../../queries/azurediagnostics.md#queries-for-microsoftnetwork)|No |