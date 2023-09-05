---
title: Supported metrics - Microsoft.ManagedNetworkFabric/internetGateways
description: Reference for Microsoft.ManagedNetworkFabric/internetGateways metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 09/04/2023
---
# Supported metrics for Microsoft.ManagedNetworkFabric/internetGateways  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.ManagedNetworkFabric/internetGateways resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Inbound active connections<p><p>Count of inbound active connections |`InboundConnectionsActive` |Count |Average |nfcId, gatewayType |Yes|
|Total inbound connections<p><p>Count of inbound connections |`InboundConnectionsTotal` |Count |Average |nfcId, gatewayType |Yes|
|Total outbound active connections<p><p>Count of outbound active connections |`OutboundConnectionsActive` |Count |Average |nfcId, gatewayType |Yes|
|Total outbound failed connections<p><p>Count of outbound total failed connections |`OutboundConnectionsFail` |Count |Average |nfcId, gatewayType |Yes|
|Total outbound connection timeouts<p><p>Count of outbound connection timeouts |`OutboundConnectionsTimeout` |Count |Average |nfcId, gatewayType |Yes|
|Total outbound connections<p><p>Count of outbound total connections |`OutboundConnectionsTotal` |Count |Maximum |nfcId, gatewayType |Yes|


<!--Gen Date:  Mon Sep 04 2023 13:11:00 GMT+0300 (Israel Daylight Time)-->