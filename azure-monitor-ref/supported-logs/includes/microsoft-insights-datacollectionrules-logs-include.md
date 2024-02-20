---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Insights/datacollectionrules, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`LogErrors` |Log Errors |[DCRLogErrors](/azure/azure-monitor/reference/tables/dcrlogerrors)<p>Errors registered during DCR-based data collection and transformation.|No|No|[Queries](../../queries/dcrlogerrors.md)|Yes |
|`LogTroubleshooting` |Log Troubleshooting |[DCRLogTroubleshooting](/azure/azure-monitor/reference/tables/dcrlogtroubleshooting)<p>Logs from DCR-based data collection and transformation to help with troubleshooting of DCR configuration and flow.|Yes|No|[Queries](../../queries/dcrlogtroubleshooting.md)|Yes |