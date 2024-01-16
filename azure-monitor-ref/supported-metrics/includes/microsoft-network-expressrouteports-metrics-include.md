---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Network/expressRoutePorts, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**AdminState**<p><p>Admin state of the port |`AdminState` |Count |Average, Minimum, Maximum, Count |`Link`|PT1M |Yes|
|**FastPathRoutesCount**<p><p>Count of fastpath routes configured on port |`FastPathRoutesCountForDirectPort` |Count |Maximum |\<none\>|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**LineProtocol**<p><p>Line protocol status of the port |`LineProtocol` |Count |Average, Minimum, Maximum, Count |`Link`|PT1M |Yes|
|**BitsInPerSecond**<p><p>Bits ingressing Azure per second |`PortBitsInPerSecond` |BitsPerSecond |Average, Minimum, Maximum, Count |`Link`|PT1M |No|
|**BitsOutPerSecond**<p><p>Bits egressing Azure per second |`PortBitsOutPerSecond` |BitsPerSecond |Average, Minimum, Maximum, Count |`Link`|PT1M |No|
|**RxLightLevel**<p><p>Rx Light level in dBm |`RxLightLevel` |Count |Average, Minimum, Maximum, Count |`Link`, `Lane`|PT1M |Yes|
|**TxLightLevel**<p><p>Tx light level in dBm |`TxLightLevel` |Count |Average, Minimum, Maximum, Count |`Link`, `Lane`|PT1M |Yes|