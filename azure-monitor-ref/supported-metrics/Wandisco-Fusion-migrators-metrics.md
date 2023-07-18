---
title: Supported metrics - Wandisco.Fusion/migrators
description: Reference for Wandisco.Fusion/migrators metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Wandisco.Fusion/migrators  
<!-- Data source : naam-->


The following table lists the metrics available for the Wandisco.Fusion/migrators resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Bytes per Second.<p><p>Throughput speed of Bytes/second being utilised for a migrator. |`BytesPerSecond` |BytesPerSecond |Average |No Dimensions |Yes|
|Directories Created Count<p><p>This provides a running view of how many directories have been created as part of a migration. |`DirectoriesCreatedCount` |Count |Total |No Dimensions |Yes|
|Files Migration Count<p><p>This provides a running total of how many files have been migrated. |`FileMigrationCount` |Count |Total |No Dimensions |Yes|
|Initial Scan Data Migrated in Bytes<p><p>This provides the view of the total bytes which have been transferred in a new migrator as a result of the initial scan of the On-Premises file system. Any data which is added to the migration after the initial scan migration, is NOT included in this metric. |`InitialScanDataMigratedInBytes` |Bytes |Total |No Dimensions |Yes|
|Live Data Migrated in Bytes<p><p>Provides a running total of LiveData which has been changed due to Client activity, since the migration started. |`LiveDataMigratedInBytes` |Bytes |Total |No Dimensions |Yes|
|Migrator CPU Load<p><p>CPU consumption by the migrator process. |`MigratorCPULoad` |Percent |Average |No Dimensions |Yes|
|Number of Excluded Paths<p><p>Provides a running count of the paths which have been excluded from the migration due to Exclusion Rules. |`NumberOfExcludedPaths` |Count |Total |No Dimensions |Yes|
|Number of Failed Paths<p><p>A count of which paths have failed to migrate. |`NumberOfFailedPaths` |Count |Total |No Dimensions |Yes|
|System CPU Load<p><p>Total CPU consumption. |`SystemCPULoad` |Percent |Average |No Dimensions |Yes|
|Total Migrated Data in Bytes<p><p>This provides a view of the successfully migrated Bytes for a given migrator |`TotalMigratedDataInBytes` |Bytes |Total |No Dimensions |Yes|
|Total Transactions<p><p>This provides a running total of the Data Transactions for which the user could be billed. |`TotalTransactions` |Count |Total |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->