---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.SignalRService/WebPubSub/replicas, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Traffic|**Connection Close Count**<p><p>The count of connections closed by various reasons. |`ConnectionCloseCount` |Count |Total |`ConnectionCloseCategory`|PT1M |Yes|
|Traffic|**Connection Open Count**<p><p>The count of new connections opened. |`ConnectionOpenCount` |Count |Total |\<none\>|PT1M |Yes|
|Traffic|**Connection Quota Utilization**<p><p>The percentage of connection connected relative to connection quota. |`ConnectionQuotaUtilization` |Percent |Minimum, Maximum, Average |\<none\>|PT1M |Yes|
|Traffic|**Inbound Traffic**<p><p>The traffic originating from outside to inside of the service. It is aggregated by adding all the bytes of the traffic. |`InboundTraffic` |Bytes |Total |\<none\>|PT1M |Yes|
|Traffic|**Outbound Traffic**<p><p>The traffic originating from inside to outside of the service. It is aggregated by adding all the bytes of the traffic. |`OutboundTraffic` |Bytes |Total |\<none\>|PT1M |Yes|
|Saturation|**Server Load**<p><p>WebPubSub server load. |`ServerLoad` |Percent |Minimum, Maximum, Average |\<none\>|PT1M |No|
|Traffic|**Connection Count**<p><p>The number of user connections established to the service. It is aggregated by adding all the online connections. |`TotalConnectionCount` |Count |Maximum, Average |\<none\>|PT1M |Yes|