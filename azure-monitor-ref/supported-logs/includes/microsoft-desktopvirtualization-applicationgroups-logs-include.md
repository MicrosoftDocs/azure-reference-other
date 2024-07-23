---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/23/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.DesktopVirtualization/applicationgroups, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`Checkpoint` |Checkpoint ||No|Yes||No |
|`Error` |Error |[WVDErrors](/azure/azure-monitor/reference/tables/wvderrors)<p>Windows Virtual Desktop Error Activity|No|Yes|[Queries](/azure/azure-monitor/reference/queries/wvderrors)|No |
|`Management` |Management |[WVDManagement](/azure/azure-monitor/reference/tables/wvdmanagement)<p>Windows Virtual Desktop Management Activity|No|Yes||No |