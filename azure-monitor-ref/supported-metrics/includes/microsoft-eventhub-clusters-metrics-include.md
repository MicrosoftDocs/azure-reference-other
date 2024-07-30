---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.EventHub/clusters, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**ActiveConnections**<br><br>Total Active Connections for Microsoft.EventHub. |`ActiveConnections` |Count |Average |\<none\>|PT1M |No|
|**Available Memory**<br><br>Available memory for the Event Hub Cluster as a percentage of total memory. |`AvailableMemory` |Percent |Maximum |`Role`|PT1M |No|
|**Capture Backlog.**<br><br>Capture Backlog for Microsoft.EventHub. |`CaptureBacklog` |Count |Total |\<none\>|PT1M |No|
|**Captured Bytes.**<br><br>Captured Bytes for Microsoft.EventHub. |`CapturedBytes` |Bytes |Total |\<none\>|PT1M |No|
|**Captured Messages.**<br><br>Captured Messages for Microsoft.EventHub. |`CapturedMessages` |Count |Total |\<none\>|PT1M |No|
|**Connections Closed.**<br><br>Connections Closed for Microsoft.EventHub. |`ConnectionsClosed` |Count |Average |\<none\>|PT1M |No|
|**Connections Opened.**<br><br>Connections Opened for Microsoft.EventHub. |`ConnectionsOpened` |Count |Average |\<none\>|PT1M |No|
|**CPU**<br><br>CPU utilization for the Event Hub Cluster as a percentage |`CPU` |Percent |Maximum |`Role`|PT1M |No|
|**Incoming Bytes.**<br><br>Incoming Bytes for Microsoft.EventHub. |`IncomingBytes` |Bytes |Total |\<none\>|PT1M |Yes|
|**Incoming Messages**<br><br>Incoming Messages for Microsoft.EventHub. |`IncomingMessages` |Count |Total |\<none\>|PT1M |Yes|
|**Incoming Requests**<br><br>Incoming Requests for Microsoft.EventHub. |`IncomingRequests` |Count |Total |\<none\>|PT1M |Yes|
|**Outgoing Bytes.**<br><br>Outgoing Bytes for Microsoft.EventHub. |`OutgoingBytes` |Bytes |Total |\<none\>|PT1M |Yes|
|**Outgoing Messages**<br><br>Outgoing Messages for Microsoft.EventHub. |`OutgoingMessages` |Count |Total |\<none\>|PT1M |Yes|
|**Quota Exceeded Errors.**<br><br>Quota Exceeded Errors for Microsoft.EventHub. |`QuotaExceededErrors` |Count |Total |`OperationResult`|PT1M |No|
|**Server Errors.**<br><br>Server Errors for Microsoft.EventHub. |`ServerErrors` |Count |Total |`OperationResult`|PT1M |No|
|**Size**<br><br>Size of an EventHub in Bytes. |`Size` |Bytes |Average, Minimum, Maximum |`Role`|PT1M |No|
|**Successful Requests**<br><br>Successful Requests for Microsoft.EventHub. |`SuccessfulRequests` |Count |Total |`OperationResult`|PT1M |No|
|**Throttled Requests.**<br><br>Throttled Requests for Microsoft.EventHub. |`ThrottledRequests` |Count |Total |`OperationResult`|PT1M |No|
|**User Errors.**<br><br>User Errors for Microsoft.EventHub. |`UserErrors` |Count |Total |`OperationResult`|PT1M |No|