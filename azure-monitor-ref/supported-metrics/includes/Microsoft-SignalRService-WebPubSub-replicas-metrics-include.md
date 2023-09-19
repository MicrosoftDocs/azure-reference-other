---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.SignalRService/WebPubSub/replicas, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Connection Close Count<p><p>The count of connections closed by various reasons. |`ConnectionCloseCount` |Count |Total |ConnectionCloseCategory|PT1M |Yes|
|Connection Open Count<p><p>The count of new connections opened. |`ConnectionOpenCount` |Count |Total |No Dimensions|PT1M |Yes|
|Connection Quota Utilization<p><p>The percentage of connection connected relative to connection quota. |`ConnectionQuotaUtilization` |Percent |Minimum, Maximum, Average |No Dimensions|PT1M |Yes|
|Inbound Traffic<p><p>The traffic originating from outside to inside of the service. It is aggregated by adding all the bytes of the traffic. |`InboundTraffic` |Bytes |Total |No Dimensions|PT1M |Yes|
|Outbound Traffic<p><p>The traffic originating from inside to outside of the service. It is aggregated by adding all the bytes of the traffic. |`OutboundTraffic` |Bytes |Total |No Dimensions|PT1M |Yes|
|Server Load<p><p>WebPubSub server load. |`ServerLoad` |Percent |Minimum, Maximum, Average |No Dimensions|PT1M |No|
|Connection Count<p><p>The number of user connections established to the service. It is aggregated by adding all the online connections. |`TotalConnectionCount` |Count |Maximum, Average |No Dimensions|PT1M |Yes|