---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.DataProtection/BackupVaults, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Backup Health Events (preview)<p><p>The count of health events pertaining to backup job health |`BackupHealthEvent` |Count |Count |dataSourceURL, backupInstanceUrl, dataSourceType, healthStatus, backupInstanceName|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Restore Health Events (preview)<p><p>The count of health events pertaining to restore job health |`RestoreHealthEvent` |Count |Count |dataSourceURL, backupInstanceUrl, dataSourceType, healthStatus, backupInstanceName|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|