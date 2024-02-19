---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.RecoveryServices/Vaults, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Health|**Backup Health Events (preview)**<br><br>The count of health events pertaining to backup job health |`BackupHealthEvent` |Count |Count |`dataSourceURL`, `backupInstanceUrl`, `dataSourceType`, `healthStatus`, `backupInstanceName`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|Health|**Restore Health Events (preview)**<br><br>The count of health events pertaining to restore job health |`RestoreHealthEvent` |Count |Count |`dataSourceURL`, `backupInstanceUrl`, `dataSourceType`, `healthStatus`, `backupInstanceName`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|