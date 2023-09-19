---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.SignalRService/SignalR, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Connection Close Count<p><p>The count of connections closed by various reasons. |`ConnectionCloseCount` |Count |Total |Endpoint, ConnectionCloseCategory|PT1M |Yes|
|Connection Count<p><p>The amount of user connection. |`ConnectionCount` |Count |Maximum |Endpoint|PT1M |Yes|
|Connection Open Count<p><p>The count of new connections opened. |`ConnectionOpenCount` |Count |Total |Endpoint|PT1M |Yes|
|Connection Quota Utilization<p><p>The percentage of connection connected relative to connection quota. |`ConnectionQuotaUtilization` |Percent |Minimum, Maximum, Average |No Dimensions|PT1M |Yes|
|Inbound Traffic<p><p>The inbound traffic of service |`InboundTraffic` |Bytes |Total |No Dimensions|PT1M |Yes|
|Message Count<p><p>The total amount of messages. |`MessageCount` |Count |Total |No Dimensions|PT1M |Yes|
|Outbound Traffic<p><p>The outbound traffic of service |`OutboundTraffic` |Bytes |Total |No Dimensions|PT1M |Yes|
|Server Load<p><p>SignalR server load. |`ServerLoad` |Percent |Minimum, Maximum, Average |No Dimensions|PT1M |No|
|System Errors<p><p>The percentage of system errors |`SystemErrors` |Percent |Maximum |No Dimensions|PT1M |Yes|
|User Errors<p><p>The percentage of user errors |`UserErrors` |Percent |Maximum |No Dimensions|PT1M |Yes|