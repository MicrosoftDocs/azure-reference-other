---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.SignalRService/SignalR, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Traffic|**Connection Close Count**<p><p>The count of connections closed by various reasons. |`ConnectionCloseCount` |Count |Total |`Endpoint`, `ConnectionCloseCategory`|PT1M |Yes|
|Traffic|**Connection Count**<p><p>The amount of user connection. |`ConnectionCount` |Count |Maximum |`Endpoint`|PT1M |Yes|
|Traffic|**Connection Open Count**<p><p>The count of new connections opened. |`ConnectionOpenCount` |Count |Total |`Endpoint`|PT1M |Yes|
|Traffic|**Connection Quota Utilization**<p><p>The percentage of connection connected relative to connection quota. |`ConnectionQuotaUtilization` |Percent |Minimum, Maximum, Average |\<none\>|PT1M |Yes|
|Traffic|**Inbound Traffic**<p><p>The inbound traffic of service |`InboundTraffic` |Bytes |Total |\<none\>|PT1M |Yes|
|Traffic|**Message Count**<p><p>The total amount of messages. |`MessageCount` |Count |Total |\<none\>|PT1M |Yes|
|Traffic|**Outbound Traffic**<p><p>The outbound traffic of service |`OutboundTraffic` |Bytes |Total |\<none\>|PT1M |Yes|
|Saturation|**Server Load**<p><p>SignalR server load. |`ServerLoad` |Percent |Minimum, Maximum, Average |\<none\>|PT1M |No|
|Errors|**System Errors**<p><p>The percentage of system errors |`SystemErrors` |Percent |Maximum |\<none\>|PT1M |Yes|
|Errors|**User Errors**<p><p>The percentage of user errors |`UserErrors` |Percent |Maximum |\<none\>|PT1M |Yes|