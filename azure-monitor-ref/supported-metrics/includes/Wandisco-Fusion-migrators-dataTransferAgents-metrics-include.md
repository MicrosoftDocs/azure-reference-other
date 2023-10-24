---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Wandisco.Fusion/migrators/dataTransferAgents, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Bytes per Second.**<p><p>Throughput speed of Bytes/second being utilised for a DTA. |`BytesPerSecond` |BytesPerSecond |Average |\<none\>|PT1M |Yes|
|**DTA CPU Load**<p><p>CPU consumption by the DTA process. |`DtaCPULoad` |Percent |Average |\<none\>|PT1M |Yes|
|**Files Migration Count**<p><p>This provides a running total of how many files have been migrated. |`FileMigrationCount` |Count |Total |\<none\>|PT1M |Yes|
|**Migrated Data in Bytes**<p><p>This provides a view of the successfully migrated Bytes for a given DTA |`MigratedDataInBytes` |Bytes |Total |\<none\>|PT1M |Yes|
|**Number of Failed Paths**<p><p>A count of which paths have failed to migrate. |`NumberOfFailedPaths` |Count |Total |\<none\>|PT1M |Yes|
|**System CPU Load**<p><p>Total CPU consumption. |`SystemCPULoad` |Percent |Average |\<none\>|PT1M |Yes|