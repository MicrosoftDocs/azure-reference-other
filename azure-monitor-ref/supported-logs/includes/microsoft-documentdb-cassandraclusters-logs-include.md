---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/21/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.DocumentDB/cassandraClusters, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`CassandraAudit` |CassandraAudit |[CassandraAudit](/azure/azure-monitor/reference/tables/cassandraaudit)<p>Detailed audit records for CQL operations and login attempts.|No|No||Yes |
|`CassandraLogs` |CassandraLogs |[CassandraLogs](/azure/azure-monitor/reference/tables/cassandralogs)<p>Cassandra general logging messages (system.log).|No|No|[Queries](/azure/azure-monitor/reference/queries/cassandralogs)|Yes |