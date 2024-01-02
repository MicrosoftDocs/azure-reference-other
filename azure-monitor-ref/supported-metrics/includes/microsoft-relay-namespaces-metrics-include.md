---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Relay/namespaces, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**ActiveConnections**<p><p>Total ActiveConnections for Microsoft.Relay. |`ActiveConnections` |Count |Total |`EntityName`|PT1M |No|
|**ActiveListeners**<p><p>Total ActiveListeners for Microsoft.Relay. |`ActiveListeners` |Count |Total |`EntityName`|PT1M |No|
|**BytesTransferred**<p><p>Total BytesTransferred for Microsoft.Relay. |`BytesTransferred` |Bytes |Total |`EntityName`|PT1M |Yes|
|**ListenerConnections-ClientError**<p><p>ClientError on ListenerConnections for Microsoft.Relay. |`ListenerConnections-ClientError` |Count |Total |`EntityName`, `OperationResult`|PT1M |No|
|**ListenerConnections-ServerError**<p><p>ServerError on ListenerConnections for Microsoft.Relay. |`ListenerConnections-ServerError` |Count |Total |`EntityName`, `OperationResult`|PT1M |No|
|**ListenerConnections-Success**<p><p>Successful ListenerConnections for Microsoft.Relay. |`ListenerConnections-Success` |Count |Total |`EntityName`, `OperationResult`|PT1M |No|
|**ListenerConnections-TotalRequests**<p><p>Total ListenerConnections for Microsoft.Relay. |`ListenerConnections-TotalRequests` |Count |Total |`EntityName`|PT1M |No|
|**ListenerDisconnects**<p><p>Total ListenerDisconnects for Microsoft.Relay. |`ListenerDisconnects` |Count |Total |`EntityName`|PT1M |No|
|**SenderConnections-ClientError**<p><p>ClientError on SenderConnections for Microsoft.Relay. |`SenderConnections-ClientError` |Count |Total |`EntityName`, `OperationResult`|PT1M |No|
|**SenderConnections-ServerError**<p><p>ServerError on SenderConnections for Microsoft.Relay. |`SenderConnections-ServerError` |Count |Total |`EntityName`, `OperationResult`|PT1M |No|
|**SenderConnections-Success**<p><p>Successful SenderConnections for Microsoft.Relay. |`SenderConnections-Success` |Count |Total |`EntityName`, `OperationResult`|PT1M |No|
|**SenderConnections-TotalRequests**<p><p>Total SenderConnections requests for Microsoft.Relay. |`SenderConnections-TotalRequests` |Count |Total |`EntityName`|PT1M |No|
|**SenderDisconnects**<p><p>Total SenderDisconnects for Microsoft.Relay. |`SenderDisconnects` |Count |Total |`EntityName`|PT1M |No|