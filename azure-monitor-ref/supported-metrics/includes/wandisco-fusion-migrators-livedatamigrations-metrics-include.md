---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Wandisco.Fusion/migrators/liveDataMigrations, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Bytes Migrated by Migration**<p><p>Provides a detailed view of a migration's Bytes Transferred |`BytesMigratedByMigration` |Bytes |Total |\<none\>|PT1M |Yes|
|**Data Transactions by Migration**<p><p>Provides a detailed view of a migration's Data Transactions |`DataTransactionsByMigration` |Count |Total |\<none\>|PT1M |Yes|
|**Directories Created Count**<p><p>This provides a running view of how many directories have been created as part of a migration. |`DirectoriesCreatedCount` |Count |Total |\<none\>|PT1M |Yes|
|**Files Migration Count**<p><p>This provides a running total of how many files have been migrated. |`FileMigrationCount` |Count |Total |\<none\>|PT1M |Yes|
|**Initial Scan Data Migrated in Bytes**<p><p>This provides the view of the total bytes which have been transferred in a new migrator as a result of the initial scan of the On-Premises file system. Any data which is added to the migration after the initial scan migration, is NOT included in this metric. |`InitialScanDataMigratedInBytes` |Bytes |Total |\<none\>|PT1M |Yes|
|**Live Data Migrated in Bytes**<p><p>Provides a running total of LiveData which has been changed due to Client activity, since the migration started. |`LiveDataMigratedInBytes` |Bytes |Total |\<none\>|PT1M |Yes|
|**Number of Excluded Paths**<p><p>Provides a running count of the paths which have been excluded from the migration due to Exclusion Rules. |`NumberOfExcludedPaths` |Count |Total |\<none\>|PT1M |Yes|
|**Number of Failed Paths**<p><p>A count of which paths have failed to migrate. |`NumberOfFailedPaths` |Count |Total |\<none\>|PT1M |Yes|
|**Recurring Scan Duration In Seconds**<p><p>The metric shows the duration in seconds of each scan. |`RecurringScanDurationInSeconds` |Count |Total |\<none\>|PT1M |Yes|
|**Total Bytes Transferred**<p><p>This metric covers how many bytes have been transferred (does not reflect how many have successfully migrated, only how much has been transferred). |`TotalBytesTransferred` |Bytes |Total |\<none\>|PT1M |Yes|
|**Total Recurring Scans**<p><p>This metric shows the count of how many scans have been completed on a recurring migration. |`TotalRecurringScans` |Count |Total |\<none\>|PT1M |Yes|