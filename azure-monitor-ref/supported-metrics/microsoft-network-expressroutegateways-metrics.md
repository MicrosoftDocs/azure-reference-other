---
title: Supported metrics - microsoft.network/expressroutegateways
description: Reference for microsoft.network/expressroutegateways metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for microsoft.network/expressroutegateways  
<!-- Data source : naam-->


The following table lists the metrics available for the microsoft.network/expressroutegateways resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Bits In Per Second<p><p>Bits per second ingressing Azure via ExpressRoute Gateway which can be further split for specific connections |`ErGatewayConnectionBitsInPerSecond` |BitsPerSecond |Average |ConnectionName |No|
|Bits Out Per Second<p><p>Bits per second egressing Azure via ExpressRoute Gateway which can be further split for specific connections |`ErGatewayConnectionBitsOutPerSecond` |BitsPerSecond |Average |ConnectionName |No|
|Active Flows<p><p>Number of Active Flows on ExpressRoute Gateway |`ExpressRouteGatewayActiveFlows` |Count |Average |roleInstance |No|
|Bits Received Per second<p><p>Total Bits received on ExpressRoute Gateway per second |`ExpressRouteGatewayBitsPerSecond` |BitsPerSecond |Average |roleInstance |No|
|Count Of Routes Advertised to Peer<p><p>Count Of Routes Advertised To Peer by ExpressRoute Gateway |`ExpressRouteGatewayCountOfRoutesAdvertisedToPeer` |Count |Maximum |roleInstance |Yes|
|Count Of Routes Learned from Peer<p><p>Count Of Routes Learned From Peer by ExpressRoute Gateway |`ExpressRouteGatewayCountOfRoutesLearnedFromPeer` |Count |Maximum |roleInstance |Yes|
|CPU utilization<p><p>CPU Utilization of the ExpressRoute Gateway |`ExpressRouteGatewayCpuUtilization` |Percent |Average |roleInstance |Yes|
|Frequency of Routes change<p><p>Frequency of Routes change in ExpressRoute Gateway |`ExpressRouteGatewayFrequencyOfRoutesChanged` |Count |Total |roleInstance |No|
|Max Flows Created Per Second<p><p>Maximum Number of Flows Created Per Second on ExpressRoute Gateway |`ExpressRouteGatewayMaxFlowsCreationRate` |CountPerSecond |Maximum |roleInstance, direction |No|
|Number of VMs in the Virtual Network<p><p>Number of VMs in the Virtual Network |`ExpressRouteGatewayNumberOfVmInVnet` |Count |Maximum |No Dimensions |No|
|Packets received per second<p><p>Total Packets received on ExpressRoute Gateway per second |`ExpressRouteGatewayPacketsPerSecond` |CountPerSecond |Average |roleInstance |No|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->