---
title: Azure Monitor tables for microsoft.networkanalytics/dataproducts
description: Azure Monitor tables for resource type microsoft.networkanalytics/dataproducts
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
   
ms.date: 03/05/2024


---

# Resource log tables for microsoft.networkanalytics/dataproducts  


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AOIDatabaseQuery](/azure/azure-monitor/reference/tables/AOIDatabaseQuery)<p>Audit logs related to queries run on database, in dataproduct environment. | audit, resources | LogManagement | Yes| [Yes](/azure/azure-monitor/reference/queries/aoidatabasequery)|
| [AOIDigestion](/azure/azure-monitor/reference/tables/AOIDigestion)<p>Logs related to digestion of files added to the input storage account. These can be used to verify that data is being successfully passed through to enrichment, or to troubleshoot issues with processing the raw data. |  | LogManagement | Yes| [Yes](/azure/azure-monitor/reference/queries/aoidigestion)|
| [AOIStorage](/azure/azure-monitor/reference/tables/AOIStorage)<p>These are Audit logs related to ingestion of files on the input storage account. | audit, resources | LogManagement | Yes| [Yes](/azure/azure-monitor/reference/queries/aoistorage)|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|

