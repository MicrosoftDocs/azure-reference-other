---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Wandisco.Fusion/migrators, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Bytes per Second.**<p><p>Throughput speed of Bytes/second being utilised for a migrator. |`BytesPerSecond` |BytesPerSecond |Average |\<none\>|PT1M |Yes|
|**Directories Created Count**<p><p>This provides a running view of how many directories have been created as part of a migration. |`DirectoriesCreatedCount` |Count |Total |\<none\>|PT1M |Yes|
|**Files Migration Count**<p><p>This provides a running total of how many files have been migrated. |`FileMigrationCount` |Count |Total |\<none\>|PT1M |Yes|
|**Initial Scan Data Migrated in Bytes**<p><p>This provides the view of the total bytes which have been transferred in a new migrator as a result of the initial scan of the On-Premises file system. Any data which is added to the migration after the initial scan migration, is NOT included in this metric. |`InitialScanDataMigratedInBytes` |Bytes |Total |\<none\>|PT1M |Yes|
|**Live Data Migrated in Bytes**<p><p>Provides a running total of LiveData which has been changed due to Client activity, since the migration started. |`LiveDataMigratedInBytes` |Bytes |Total |\<none\>|PT1M |Yes|
|**Migrator CPU Load**<p><p>CPU consumption by the migrator process. |`MigratorCPULoad` |Percent |Average |\<none\>|PT1M |Yes|
|**Number of Excluded Paths**<p><p>Provides a running count of the paths which have been excluded from the migration due to Exclusion Rules. |`NumberOfExcludedPaths` |Count |Total |\<none\>|PT1M |Yes|
|**Number of Failed Paths**<p><p>A count of which paths have failed to migrate. |`NumberOfFailedPaths` |Count |Total |\<none\>|PT1M |Yes|
|**System CPU Load**<p><p>Total CPU consumption. |`SystemCPULoad` |Percent |Average |\<none\>|PT1M |Yes|
|**Total Migrated Data in Bytes**<p><p>This provides a view of the successfully migrated Bytes for a given migrator |`TotalMigratedDataInBytes` |Bytes |Total |\<none\>|PT1M |Yes|
|**Total Transactions**<p><p>This provides a running total of the Data Transactions for which the user could be billed. |`TotalTransactions` |Count |Total |\<none\>|PT1M |Yes|