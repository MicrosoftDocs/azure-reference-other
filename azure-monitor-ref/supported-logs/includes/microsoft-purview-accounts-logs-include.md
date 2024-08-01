---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: microsoft.purview/accounts, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`DataSensitivityLogEvent` |DataSensitivity |[PurviewDataSensitivityLogs](/azure/azure-monitor/reference/tables/purviewdatasensitivitylogs)<p>Data Sensitivity information for assets scanned using Purview.|No|No||Yes |
|`ScanStatusLogEvent` |ScanStatus |[PurviewScanStatusLogs](/azure/azure-monitor/reference/tables/purviewscanstatuslogs)<p>Status of the scan on the data sources.|No|Yes||No |
|`Security` |PurviewAccountAuditEvents |[PurviewSecurityLogs](/azure/azure-monitor/reference/tables/purviewsecuritylogs)<p>Table containing audit events for the Purview account, such as role assignments to a collection or creation or deletion of a collection.|No|No|[Queries](/azure/azure-monitor/reference/queries/purviewsecuritylogs)|Yes |