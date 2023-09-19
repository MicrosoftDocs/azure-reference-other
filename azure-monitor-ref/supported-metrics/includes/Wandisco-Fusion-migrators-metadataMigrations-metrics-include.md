---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Wandisco.Fusion/migrators/metadataMigrations, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Hive Items Added After Scan<p><p>Provides a running total of how many items have been added after the initial scan. |`LiveHiveAddedAfterScan` |Count |Total |No Dimensions|PT1M |Yes|
|Discovered Hive Items<p><p>Provides a running total of how many items have been discovered. |`LiveHiveDiscoveredItems` |Count |Total |No Dimensions|PT1M |Yes|
|Initially Discovered Hive Items<p><p>This provides the view of the total items discovered as a result of the initial scan of the On-Premises file system. Any items that are discovered after the initial scan, are NOT included in this metric. |`LiveHiveInitiallyDiscoveredItems` |Count |Total |No Dimensions|PT1M |Yes|
|Initially Migrated Hive Items<p><p>This provides the view of the total items migrated as a result of the initial scan of the On-Premises file system. Any items that are added after the initial scan, are NOT included in this metric. |`LiveHiveInitiallyMigratedItems` |Count |Total |No Dimensions|PT1M |Yes|
|Migrated Hive Items<p><p>Provides a running total of how many items have been migrated. |`LiveHiveMigratedItems` |Count |Total |No Dimensions|PT1M |Yes|