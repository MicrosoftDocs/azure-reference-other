---
title: Supported metrics - Microsoft.Relay/namespaces
description: Reference for Microsoft.Relay/namespaces metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Relay/namespaces  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Relay/namespaces resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|ActiveConnections<p><p>Total ActiveConnections for Microsoft.Relay. |`ActiveConnections` |Count |Total |EntityName |No|
|ActiveListeners<p><p>Total ActiveListeners for Microsoft.Relay. |`ActiveListeners` |Count |Total |EntityName |No|
|BytesTransferred<p><p>Total BytesTransferred for Microsoft.Relay. |`BytesTransferred` |Bytes |Total |EntityName |Yes|
|ListenerConnections-ClientError<p><p>ClientError on ListenerConnections for Microsoft.Relay. |`ListenerConnections-ClientError` |Count |Total |EntityName, OperationResult |No|
|ListenerConnections-ServerError<p><p>ServerError on ListenerConnections for Microsoft.Relay. |`ListenerConnections-ServerError` |Count |Total |EntityName, OperationResult |No|
|ListenerConnections-Success<p><p>Successful ListenerConnections for Microsoft.Relay. |`ListenerConnections-Success` |Count |Total |EntityName, OperationResult |No|
|ListenerConnections-TotalRequests<p><p>Total ListenerConnections for Microsoft.Relay. |`ListenerConnections-TotalRequests` |Count |Total |EntityName |No|
|ListenerDisconnects<p><p>Total ListenerDisconnects for Microsoft.Relay. |`ListenerDisconnects` |Count |Total |EntityName |No|
|SenderConnections-ClientError<p><p>ClientError on SenderConnections for Microsoft.Relay. |`SenderConnections-ClientError` |Count |Total |EntityName, OperationResult |No|
|SenderConnections-ServerError<p><p>ServerError on SenderConnections for Microsoft.Relay. |`SenderConnections-ServerError` |Count |Total |EntityName, OperationResult |No|
|SenderConnections-Success<p><p>Successful SenderConnections for Microsoft.Relay. |`SenderConnections-Success` |Count |Total |EntityName, OperationResult |No|
|SenderConnections-TotalRequests<p><p>Total SenderConnections requests for Microsoft.Relay. |`SenderConnections-TotalRequests` |Count |Total |EntityName |No|
|SenderDisconnects<p><p>Total SenderDisconnects for Microsoft.Relay. |`SenderDisconnects` |Count |Total |EntityName |No|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->