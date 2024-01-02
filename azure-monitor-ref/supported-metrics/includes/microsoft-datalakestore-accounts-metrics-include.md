---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.DataLakeStore/accounts, arm
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Data Read**<p><p>Total amount of data read from the account. |`DataRead` |Bytes |Total |\<none\>|PT1M, PT1H |Yes|
|**Data Written**<p><p>Total amount of data written to the account. |`DataWritten` |Bytes |Total |\<none\>|PT1M, PT1H |Yes|
|**Read Requests**<p><p>Count of data read requests to the account. |`ReadRequests` |Count |Total |\<none\>|PT1M, PT1H |Yes|
|**Total Storage**<p><p>Total amount of data stored in the account. |`TotalStorage` |Bytes |Maximum |\<none\>|PT1M, PT1H |Yes|
|**Write Requests**<p><p>Count of data write requests to the account. |`WriteRequests` |Count |Total |\<none\>|PT1M, PT1H |Yes|