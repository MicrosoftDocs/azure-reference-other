---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.purview/accounts
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [PurviewDataSensitivityLogs](/azure/azure-monitor/reference/tables/PurviewDataSensitivityLogs)<p>Data Sensitivity information for assets scanned using Purview. | security, resources | LogManagement | No| -|
| [PurviewScanStatusLogs](/azure/azure-monitor/reference/tables/PurviewScanStatusLogs)<p>Status of the scan on the data sources. | resources | LogManagement | No| -|
| [PurviewSecurityLogs](/azure/azure-monitor/reference/tables/PurviewSecurityLogs)<p>Table containing audit events for the Purview account, such as role assignments to a collection or creation or deletion of a collection. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/purviewsecuritylogs)|

  
