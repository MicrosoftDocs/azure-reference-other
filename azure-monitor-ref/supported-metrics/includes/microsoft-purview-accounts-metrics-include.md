---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: microsoft.purview/accounts, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Data Map Capacity Units**<br><br>Indicates Data Map Capacity Units. |`DataMapCapacityUnits` |Count |Total, Count |\<none\>|PT1H, P1D |Yes|
|**Data Map Storage Size**<br><br>Indicates the data map storage size. |`DataMapStorageSize` |Bytes |Total, Average |\<none\>|PT1H, P1D |Yes|
|**Scan Cancelled**<br><br>Indicates the number of scans cancelled. |`ScanCancelled` |Count |Total, Count |\<none\>|PT1M, PT15M, PT1H, P1D |Yes|
|**Scan Completed**<br><br>Indicates the number of scans completed successfully. |`ScanCompleted` |Count |Total, Count |\<none\>|PT1M, PT15M, PT1H, P1D |Yes|
|**Scan Failed**<br><br>Indicates the number of scans failed. |`ScanFailed` |Count |Total, Count |\<none\>|PT1M, PT15M, PT1H, P1D |Yes|
|**Scan time taken**<br><br>Indicates the total scan time in seconds. |`ScanTimeTaken` |Seconds |Minimum, Maximum, Total, Average |\<none\>|PT1M, PT15M, PT1H, P1D |Yes|