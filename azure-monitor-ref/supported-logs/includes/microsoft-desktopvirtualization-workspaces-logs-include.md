---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/02/2024
ms.author: orens
author: osalzberg
ms.custom: Microsoft.DesktopVirtualization/workspaces, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`Checkpoint` |Checkpoint ||No|No||No |
|`Error` |Error |[WVDErrors](/azure/azure-monitor/reference/tables/wvderrors)<p>Windows Virtual Desktop Error Activity|No|Yes|[Queries](/azure/azure-monitor/reference/queries/wvderrors)|No |
|`Feed` |Feed |[WVDFeeds](/azure/azure-monitor/reference/tables/wvdfeeds)<p>Windows Virtual Desktop Feed Activity|No|Yes||No |
|`Management` |Management |[WVDManagement](/azure/azure-monitor/reference/tables/wvdmanagement)<p>Windows Virtual Desktop Management Activity|No|Yes||No |