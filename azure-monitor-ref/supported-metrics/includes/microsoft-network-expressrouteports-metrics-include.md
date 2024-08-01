---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.Network/expressRoutePorts, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**AdminState**<br><br>Admin state of the port |`AdminState` |Count |Average, Minimum, Maximum, Count |`Link`|PT1M |Yes|
|**FastPathRoutesCount**<br><br>Count of fastpath routes configured on port |`FastPathRoutesCountForDirectPort` |Count |Maximum |\<none\>|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**LineProtocol**<br><br>Line protocol status of the port |`LineProtocol` |Count |Average, Minimum, Maximum, Count |`Link`|PT1M |Yes|
|**BitsInPerSecond**<br><br>Bits ingressing Azure per second |`PortBitsInPerSecond` |BitsPerSecond |Average, Minimum, Maximum, Count |`Link`|PT1M |No|
|**BitsOutPerSecond**<br><br>Bits egressing Azure per second |`PortBitsOutPerSecond` |BitsPerSecond |Average, Minimum, Maximum, Count |`Link`|PT1M |No|
|**RxLightLevel**<br><br>Rx Light level in dBm |`RxLightLevel` |Count |Average, Minimum, Maximum, Count |`Link`, `Lane`|PT1M |Yes|
|**TxLightLevel**<br><br>Tx light level in dBm |`TxLightLevel` |Count |Average, Minimum, Maximum, Count |`Link`, `Lane`|PT1M |Yes|