---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.DataProtection/BackupVaults, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Backup Health Events (preview)**<p><p>The count of health events pertaining to backup job health |`BackupHealthEvent` |Count |Count |`dataSourceURL`, `backupInstanceUrl`, `dataSourceType`, `healthStatus`, `backupInstanceName`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Restore Health Events (preview)**<p><p>The count of health events pertaining to restore job health |`RestoreHealthEvent` |Count |Count |`dataSourceURL`, `backupInstanceUrl`, `dataSourceType`, `healthStatus`, `backupInstanceName`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|