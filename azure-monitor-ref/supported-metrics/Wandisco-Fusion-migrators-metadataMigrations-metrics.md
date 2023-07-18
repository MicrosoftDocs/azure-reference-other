---
title: Supported metrics - Wandisco.Fusion/migrators/metadataMigrations
description: Reference for Wandisco.Fusion/migrators/metadataMigrations metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Wandisco.Fusion/migrators/metadataMigrations  
<!-- Data source : naam-->


The following table lists the metrics available for the Wandisco.Fusion/migrators/metadataMigrations resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Hive Items Added After Scan<p><p>Provides a running total of how many items have been added after the initial scan. |`LiveHiveAddedAfterScan` |Count |Total |No Dimensions |Yes|
|Discovered Hive Items<p><p>Provides a running total of how many items have been discovered. |`LiveHiveDiscoveredItems` |Count |Total |No Dimensions |Yes|
|Initially Discovered Hive Items<p><p>This provides the view of the total items discovered as a result of the initial scan of the On-Premises file system. Any items that are discovered after the initial scan, are NOT included in this metric. |`LiveHiveInitiallyDiscoveredItems` |Count |Total |No Dimensions |Yes|
|Initially Migrated Hive Items<p><p>This provides the view of the total items migrated as a result of the initial scan of the On-Premises file system. Any items that are added after the initial scan, are NOT included in this metric. |`LiveHiveInitiallyMigratedItems` |Count |Total |No Dimensions |Yes|
|Migrated Hive Items<p><p>Provides a running total of how many items have been migrated. |`LiveHiveMigratedItems` |Count |Total |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->