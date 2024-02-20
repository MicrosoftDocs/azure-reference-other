---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.AutonomousDevelopmentPlatform/workspaces, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`Audit` |Audit |[ADPAudit](/azure/azure-monitor/reference/tables/adpaudit)<p>Audit entries for ADP operations.|No|Yes||Yes |
|`Operational` |Operational |[ADPDiagnostics](/azure/azure-monitor/reference/tables/adpdiagnostics)<p>Diagnostic logs of the ADP service.|No|Yes||Yes |
|`Request` |Request |[ADPRequests](/azure/azure-monitor/reference/tables/adprequests)<p>Requests made to the ADP service.|No|Yes||Yes |