---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.DataLakeStore/accounts, arm
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Data Read<p><p>Total amount of data read from the account. |`DataRead` |Bytes |Total |No Dimensions|PT1M, PT1H |Yes|
|Data Written<p><p>Total amount of data written to the account. |`DataWritten` |Bytes |Total |No Dimensions|PT1M, PT1H |Yes|
|Read Requests<p><p>Count of data read requests to the account. |`ReadRequests` |Count |Total |No Dimensions|PT1M, PT1H |Yes|
|Total Storage<p><p>Total amount of data stored in the account. |`TotalStorage` |Bytes |Maximum |No Dimensions|PT1M, PT1H |Yes|
|Write Requests<p><p>Count of data write requests to the account. |`WriteRequests` |Count |Total |No Dimensions|PT1M, PT1H |Yes|