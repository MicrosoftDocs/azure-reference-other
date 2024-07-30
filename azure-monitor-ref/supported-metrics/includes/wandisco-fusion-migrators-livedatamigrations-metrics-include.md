---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Wandisco.Fusion/migrators/liveDataMigrations, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Bytes Migrated by Migration**<br><br>Provides a detailed view of a migration's Bytes Transferred |`BytesMigratedByMigration` |Bytes |Total |\<none\>|PT1M |Yes|
|**Data Transactions by Migration**<br><br>Provides a detailed view of a migration's Data Transactions |`DataTransactionsByMigration` |Count |Total |\<none\>|PT1M |Yes|
|**Directories Created Count**<br><br>This provides a running view of how many directories have been created as part of a migration. |`DirectoriesCreatedCount` |Count |Total |\<none\>|PT1M |Yes|
|**Files Migration Count**<br><br>This provides a running total of how many files have been migrated. |`FileMigrationCount` |Count |Total |\<none\>|PT1M |Yes|
|**Initial Scan Data Migrated in Bytes**<br><br>This provides the view of the total bytes which have been transferred in a new migrator as a result of the initial scan of the On-Premises file system. Any data which is added to the migration after the initial scan migration, is NOT included in this metric. |`InitialScanDataMigratedInBytes` |Bytes |Total |\<none\>|PT1M |Yes|
|**Live Data Migrated in Bytes**<br><br>Provides a running total of LiveData which has been changed due to Client activity, since the migration started. |`LiveDataMigratedInBytes` |Bytes |Total |\<none\>|PT1M |Yes|
|**Number of Excluded Paths**<br><br>Provides a running count of the paths which have been excluded from the migration due to Exclusion Rules. |`NumberOfExcludedPaths` |Count |Total |\<none\>|PT1M |Yes|
|**Number of Failed Paths**<br><br>A count of which paths have failed to migrate. |`NumberOfFailedPaths` |Count |Total |\<none\>|PT1M |Yes|
|**Recurring Scan Duration In Seconds**<br><br>The metric shows the duration in seconds of each scan. |`RecurringScanDurationInSeconds` |Count |Total |\<none\>|PT1M |Yes|
|**Total Bytes Transferred**<br><br>This metric covers how many bytes have been transferred (does not reflect how many have successfully migrated, only how much has been transferred). |`TotalBytesTransferred` |Bytes |Total |\<none\>|PT1M |Yes|
|**Total Recurring Scans**<br><br>This metric shows the count of how many scans have been completed on a recurring migration. |`TotalRecurringScans` |Count |Total |\<none\>|PT1M |Yes|