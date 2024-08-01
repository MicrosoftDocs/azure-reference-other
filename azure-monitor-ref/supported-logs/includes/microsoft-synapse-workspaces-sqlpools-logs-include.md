---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: Microsoft.Synapse/workspaces/sqlPools, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`DmsWorkers` |Dms Workers |[SynapseSqlPoolDmsWorkers](/azure/azure-monitor/reference/tables/synapsesqlpooldmsworkers)<p>Information about workers completing DMS steps in an Azure Synapse dedicated SQL pool.|Yes|Yes||No |
|`ExecRequests` |Exec Requests |[SynapseSqlPoolExecRequests](/azure/azure-monitor/reference/tables/synapsesqlpoolexecrequests)<p>Information about SQL requests or queries in an Azure Synapse dedicated SQL pool.|Yes|Yes||No |
|`RequestSteps` |Request Steps |[SynapseSqlPoolRequestSteps](/azure/azure-monitor/reference/tables/synapsesqlpoolrequeststeps)<p>Information about request steps that compose a given SQL request or query in an Azure Synapse dedicated SQL pool.|Yes|Yes||No |
|`SqlRequests` |Sql Requests |[SynapseSqlPoolSqlRequests](/azure/azure-monitor/reference/tables/synapsesqlpoolsqlrequests)<p>Information about query distributions of the steps of SQL requests/queries in an Azure Synapse dedicated SQL pool.|Yes|Yes||No |
|`SQLSecurityAuditEvents` |Sql Security Audit Event |[SQLSecurityAuditEvents](/azure/azure-monitor/reference/tables/sqlsecurityauditevents)<p>Azure Synapse SQL Audit Log.|No|Yes||No |
|`Waits` |Waits |[SynapseSqlPoolWaits](/azure/azure-monitor/reference/tables/synapsesqlpoolwaits)<p>Information about the wait states encountered during execution of a SQL request/query in an Azure Synapse dedicated SQL pool, including locks and waits on transmission queues.|Yes|Yes||No |