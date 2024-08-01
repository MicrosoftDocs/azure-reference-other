---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.Web/serverfarms, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Data In**<br><br>The average incoming bandwidth used across all instances of the plan. |`BytesReceived` |Bytes |Total |`Instance`|PT1M |Yes|
|**Data Out**<br><br>The average outgoing bandwidth used across all instances of the plan. |`BytesSent` |Bytes |Total |`Instance`|PT1M |Yes|
|**CPU Percentage**<br><br>The average CPU used across all instances of the plan. |`CpuPercentage` |Percent |Average |`Instance`|PT1M |Yes|
|**Disk Queue Length**<br><br>The average number of both read and write requests that were queued on storage. A high disk queue length is an indication of an app that might be slowing down because of excessive disk I/O. |`DiskQueueLength` |Count |Average |`Instance`|PT1M |Yes|
|**Http Queue Length**<br><br>The average number of HTTP requests that had to sit on the queue before being fulfilled. A high or increasing HTTP Queue length is a symptom of a plan under heavy load. |`HttpQueueLength` |Count |Average |`Instance`|PT1M |Yes|
|**Memory Percentage**<br><br>The average memory used across all instances of the plan. |`MemoryPercentage` |Percent |Average |`Instance`|PT1M |Yes|
|**Socket Count for Inbound Requests**<br><br>The average number of sockets used for incoming HTTP requests across all the instances of the plan. |`SocketInboundAll` |Count |Average |`Instance`|PT1M |Yes|
|**Socket Count for Loopback Connections**<br><br>The average number of sockets used for loopback connections across all the instances of the plan. |`SocketLoopback` |Count |Average |`Instance`|PT1M |Yes|
|**Socket Count of Outbound Requests**<br><br>The average number of sockets used for outbound connections across all the instances of the plan irrespective of their TCP states. Having too many outbound connections can cause connectivity errors. |`SocketOutboundAll` |Count |Average |`Instance`|PT1M |Yes|
|**Established Socket Count for Outbound Requests**<br><br>The average number of sockets in ESTABLISHED state used for outbound connections across all the instances of the plan. |`SocketOutboundEstablished` |Count |Average |`Instance`|PT1M |Yes|
|**Time Wait Socket Count for Outbound Requests**<br><br>The average number of sockets in TIME_WAIT state used for outbound connections across all the instances of the plan. High or increasing outbound socket counts in TIME_WAIT state can cause connectivity errors. |`SocketOutboundTimeWait` |Count |Average |`Instance`|PT1M |Yes|
|**TCP Close Wait**<br><br>The average number of sockets in CLOSE_WAIT state across all the instances of the plan. |`TcpCloseWait` |Count |Average |`Instance`|PT1M |Yes|
|**TCP Closing**<br><br>The average number of sockets in CLOSING state across all the instances of the plan. |`TcpClosing` |Count |Average |`Instance`|PT1M |Yes|
|**TCP Established**<br><br>The average number of sockets in ESTABLISHED state across all the instances of the plan. |`TcpEstablished` |Count |Average |`Instance`|PT1M |Yes|
|**TCP Fin Wait 1**<br><br>The average number of sockets in FIN_WAIT_1 state across all the instances of the plan. |`TcpFinWait1` |Count |Average |`Instance`|PT1M |Yes|
|**TCP Fin Wait 2**<br><br>The average number of sockets in FIN_WAIT_2 state across all the instances of the plan. |`TcpFinWait2` |Count |Average |`Instance`|PT1M |Yes|
|**TCP Last Ack**<br><br>The average number of sockets in LAST_ACK state across all the instances of the plan. |`TcpLastAck` |Count |Average |`Instance`|PT1M |Yes|
|**TCP Syn Received**<br><br>The average number of sockets in SYN_RCVD state across all the instances of the plan. |`TcpSynReceived` |Count |Average |`Instance`|PT1M |Yes|
|**TCP Syn Sent**<br><br>The average number of sockets in SYN_SENT state across all the instances of the plan. |`TcpSynSent` |Count |Average |`Instance`|PT1M |Yes|
|**TCP Time Wait**<br><br>The average number of sockets in TIME_WAIT state across all the instances of the plan. |`TcpTimeWait` |Count |Average |`Instance`|PT1M |Yes|