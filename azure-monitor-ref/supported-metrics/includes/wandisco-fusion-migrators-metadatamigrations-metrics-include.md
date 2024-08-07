---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Wandisco.Fusion/migrators/metadataMigrations, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Hive Items Added After Scan**<br><br>Provides a running total of how many items have been added after the initial scan. |`LiveHiveAddedAfterScan` |Count |Total |\<none\>|PT1M |Yes|
|**Discovered Hive Items**<br><br>Provides a running total of how many items have been discovered. |`LiveHiveDiscoveredItems` |Count |Total |\<none\>|PT1M |Yes|
|**Initially Discovered Hive Items**<br><br>This provides the view of the total items discovered as a result of the initial scan of the On-Premises file system. Any items that are discovered after the initial scan, are NOT included in this metric. |`LiveHiveInitiallyDiscoveredItems` |Count |Total |\<none\>|PT1M |Yes|
|**Initially Migrated Hive Items**<br><br>This provides the view of the total items migrated as a result of the initial scan of the On-Premises file system. Any items that are added after the initial scan, are NOT included in this metric. |`LiveHiveInitiallyMigratedItems` |Count |Total |\<none\>|PT1M |Yes|
|**Migrated Hive Items**<br><br>Provides a running total of how many items have been migrated. |`LiveHiveMigratedItems` |Count |Total |\<none\>|PT1M |Yes|