---
ms.service: azure-monitor
ms.topic: include
ms.date: 05/06/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.DataShare/accounts, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`ReceivedShareSnapshots` |Received Share Snapshots |[MicrosoftDataShareReceivedSnapshotLog](/azure/azure-monitor/reference/tables/microsoftdatasharereceivedsnapshotlog)<p>Data Share consumer side synchronization logs.|No|Yes|[Queries](/azure/azure-monitor/reference/queries/microsoftdatasharereceivedsnapshotlog)|No |
|`SentShareSnapshots` |Sent Share Snapshots |[MicrosoftDataShareSentSnapshotLog](/azure/azure-monitor/reference/tables/microsoftdatasharesentsnapshotlog)<p>Data Share provider side synchronization logs.|No|Yes|[Queries](/azure/azure-monitor/reference/queries/microsoftdatasharesentsnapshotlog)|No |
|`Shares` |Shares |[MicrosoftDataShareShareLog](/azure/azure-monitor/reference/tables/microsoftdatasharesharelog)<p>Microsoft Data Share Share Log|No|No||No |
|`ShareSubscriptions` |Share Subscriptions ||No|No||No |