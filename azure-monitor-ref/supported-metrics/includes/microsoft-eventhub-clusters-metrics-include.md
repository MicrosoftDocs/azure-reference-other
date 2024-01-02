---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.EventHub/clusters, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**ActiveConnections**<p><p>Total Active Connections for Microsoft.EventHub. |`ActiveConnections` |Count |Average |\<none\>|PT1M |No|
|**Available Memory**<p><p>Available memory for the Event Hub Cluster as a percentage of total memory. |`AvailableMemory` |Percent |Maximum |`Role`|PT1M |No|
|**Capture Backlog.**<p><p>Capture Backlog for Microsoft.EventHub. |`CaptureBacklog` |Count |Total |\<none\>|PT1M |No|
|**Captured Bytes.**<p><p>Captured Bytes for Microsoft.EventHub. |`CapturedBytes` |Bytes |Total |\<none\>|PT1M |No|
|**Captured Messages.**<p><p>Captured Messages for Microsoft.EventHub. |`CapturedMessages` |Count |Total |\<none\>|PT1M |No|
|**Connections Closed.**<p><p>Connections Closed for Microsoft.EventHub. |`ConnectionsClosed` |Count |Average |\<none\>|PT1M |No|
|**Connections Opened.**<p><p>Connections Opened for Microsoft.EventHub. |`ConnectionsOpened` |Count |Average |\<none\>|PT1M |No|
|**CPU**<p><p>CPU utilization for the Event Hub Cluster as a percentage |`CPU` |Percent |Maximum |`Role`|PT1M |No|
|**Incoming Bytes.**<p><p>Incoming Bytes for Microsoft.EventHub. |`IncomingBytes` |Bytes |Total |\<none\>|PT1M |Yes|
|**Incoming Messages**<p><p>Incoming Messages for Microsoft.EventHub. |`IncomingMessages` |Count |Total |\<none\>|PT1M |Yes|
|**Incoming Requests**<p><p>Incoming Requests for Microsoft.EventHub. |`IncomingRequests` |Count |Total |\<none\>|PT1M |Yes|
|**Outgoing Bytes.**<p><p>Outgoing Bytes for Microsoft.EventHub. |`OutgoingBytes` |Bytes |Total |\<none\>|PT1M |Yes|
|**Outgoing Messages**<p><p>Outgoing Messages for Microsoft.EventHub. |`OutgoingMessages` |Count |Total |\<none\>|PT1M |Yes|
|**Quota Exceeded Errors.**<p><p>Quota Exceeded Errors for Microsoft.EventHub. |`QuotaExceededErrors` |Count |Total |`OperationResult`|PT1M |No|
|**Server Errors.**<p><p>Server Errors for Microsoft.EventHub. |`ServerErrors` |Count |Total |`OperationResult`|PT1M |No|
|**Size**<p><p>Size of an EventHub in Bytes. |`Size` |Bytes |Average, Minimum, Maximum |`Role`|PT1M |No|
|**Successful Requests**<p><p>Successful Requests for Microsoft.EventHub. |`SuccessfulRequests` |Count |Total |`OperationResult`|PT1M |No|
|**Throttled Requests.**<p><p>Throttled Requests for Microsoft.EventHub. |`ThrottledRequests` |Count |Total |`OperationResult`|PT1M |No|
|**User Errors.**<p><p>User Errors for Microsoft.EventHub. |`UserErrors` |Count |Total |`OperationResult`|PT1M |No|