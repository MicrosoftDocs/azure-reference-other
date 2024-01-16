---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: microsoft.purview/accounts, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Data Map Capacity Units**<p><p>Indicates Data Map Capacity Units. |`DataMapCapacityUnits` |Count |Total, Count |\<none\>|PT1H, P1D |Yes|
|**Data Map Storage Size**<p><p>Indicates the data map storage size. |`DataMapStorageSize` |Bytes |Total, Average |\<none\>|PT1H, P1D |Yes|
|**Scan Cancelled**<p><p>Indicates the number of scans cancelled. |`ScanCancelled` |Count |Total, Count |\<none\>|PT1M, PT15M, PT1H, P1D |Yes|
|**Scan Completed**<p><p>Indicates the number of scans completed successfully. |`ScanCompleted` |Count |Total, Count |\<none\>|PT1M, PT15M, PT1H, P1D |Yes|
|**Scan Failed**<p><p>Indicates the number of scans failed. |`ScanFailed` |Count |Total, Count |\<none\>|PT1M, PT15M, PT1H, P1D |Yes|
|**Scan time taken**<p><p>Indicates the total scan time in seconds. |`ScanTimeTaken` |Seconds |Minimum, Maximum, Total, Average |\<none\>|PT1M, PT15M, PT1H, P1D |Yes|