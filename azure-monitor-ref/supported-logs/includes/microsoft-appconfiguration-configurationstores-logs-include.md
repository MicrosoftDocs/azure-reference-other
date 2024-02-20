---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.AppConfiguration/configurationStores, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`Audit` |Audit |[AACAudit](/azure/azure-monitor/reference/tables/aacaudit)<p>Azure App Configuration audit logs.|No|Yes|[Queries](../../queries/aacaudit.md)|Yes |
|`HttpRequest` |HTTP Requests |[AACHttpRequest](/azure/azure-monitor/reference/tables/aachttprequest)<p>Incoming requests to Azure App Configuration. The records in this table are aggregated. The 'HitCount' field describes the number of requests that each record accounts for.|No|Yes|[Queries](../../queries/aachttprequest.md)|Yes |