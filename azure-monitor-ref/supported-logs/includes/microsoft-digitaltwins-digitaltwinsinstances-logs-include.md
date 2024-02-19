---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.DigitalTwins/digitalTwinsInstances, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`DataHistoryOperation` |DataHistoryOperation ||No|No||Yes |
|`DigitalTwinsOperation` |DigitalTwinsOperation |[ADTDigitalTwinsOperation](/azure/azure-monitor/reference/tables/adtdigitaltwinsoperation)<p>Schema for Azure Digital Twins' Digital Twin operations. The Digital Twins Operation category tracks all customer requests to manage a digital twin, including CRUD on Twins and Relationships.|No|Yes|[Queries](../../queries/adtdigitaltwinsoperation.md)|No |
|`EventRoutesOperation` |EventRoutesOperation |[ADTEventRoutesOperation](/azure/azure-monitor/reference/tables/adteventroutesoperation)<p>Schema for Azure Digital Twins' Event Routes operations. The Event Routes Operation category tracks all events being published to endpoints, which are other Azure services.|No|Yes|[Queries](../../queries/adteventroutesoperation.md)|No |
|`ModelsOperation` |ModelsOperation |[ADTModelsOperation](/azure/azure-monitor/reference/tables/adtmodelsoperation)<p>Schema for Azure Digital Twins' Models operations. The Models Operation category tracks all customer requests to manage models in a digital twins instance.|No|Yes|[Queries](../../queries/adtmodelsoperation.md)|No |
|`QueryOperation` |QueryOperation |[ADTQueryOperation](/azure/azure-monitor/reference/tables/adtqueryoperation)<p>Schema for Azure Digital Twins' Query operations. The Query Operation category tracks all customer requests to query their digital twins instance.|No|Yes|[Queries](../../queries/adtqueryoperation.md)|No |
|`ResourceProviderOperation` |ResourceProviderOperation ||No|Yes||Yes |