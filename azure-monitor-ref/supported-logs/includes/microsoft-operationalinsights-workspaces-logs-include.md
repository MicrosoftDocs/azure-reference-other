---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.OperationalInsights/workspaces, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`Audit` |Audit |[LAQueryLogs](/azure/azure-monitor/reference/tables/laquerylogs)<p>Audit logs for queries executed in Log Analytics Workspaces.|No|Yes|[Queries](../../queries/laquerylogs.md)|No |
|`SummaryLogs` |Summary Logs |[LASummaryLogs](/azure/azure-monitor/reference/tables/lasummarylogs)<p>Provides Summary logs rules execution details, including run status, duration and errors. Can be used to view bins executions statuses, identify rules that take a long time to complete, and failures that could be optimized in query, or shorted bin time.|Yes|No|[Queries](../../queries/lasummarylogs.md)|Yes |