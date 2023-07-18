---
title: Supported metrics - microsoft.network/virtualnetworkgateways
description: Reference for microsoft.network/virtualnetworkgateways metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for microsoft.network/virtualnetworkgateways  
<!-- Data source : naam-->


The following table lists the metrics available for the microsoft.network/virtualnetworkgateways resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Gateway S2S Bandwidth<p><p>Site-to-site bandwidth of a gateway in bytes per second |`AverageBandwidth` |BytesPerSecond |Average |Instance |Yes|
|BGP Peer Status<p><p>Status of BGP peer |`BgpPeerStatus` |Count |Average |BgpPeerAddress, Instance |No|
|BGP Routes Advertised<p><p>Count of Bgp Routes Advertised through tunnel |`BgpRoutesAdvertised` |Count |Total |BgpPeerAddress, Instance |Yes|
|BGP Routes Learned<p><p>Count of Bgp Routes Learned through tunnel |`BgpRoutesLearned` |Count |Total |BgpPeerAddress, Instance |Yes|
|Active Flows<p><p>Number of Active Flows on ExpressRoute Gateway |`ExpressRouteGatewayActiveFlows` |Count |Average |roleInstance |No|
|Bits Received Per second<p><p>Total Bits received on ExpressRoute Gateway per second |`ExpressRouteGatewayBitsPerSecond` |BitsPerSecond |Average |roleInstance |No|
|Count Of Routes Advertised to Peer<p><p>Count Of Routes Advertised To Peer by ExpressRoute Gateway |`ExpressRouteGatewayCountOfRoutesAdvertisedToPeer` |Count |Maximum |roleInstance |Yes|
|Count Of Routes Learned from Peer<p><p>Count Of Routes Learned From Peer by ExpressRoute Gateway |`ExpressRouteGatewayCountOfRoutesLearnedFromPeer` |Count |Maximum |roleInstance |Yes|
|CPU utilization<p><p>CPU Utilization of the ExpressRoute Gateway |`ExpressRouteGatewayCpuUtilization` |Percent |Average |roleInstance |Yes|
|Frequency of Routes change<p><p>Frequency of Routes change in ExpressRoute Gateway |`ExpressRouteGatewayFrequencyOfRoutesChanged` |Count |Total |roleInstance |No|
|Max Flows Created Per Second<p><p>Maximum Number of Flows Created Per Second on ExpressRoute Gateway |`ExpressRouteGatewayMaxFlowsCreationRate` |CountPerSecond |Maximum |roleInstance, direction |No|
|Number of VMs in the Virtual Network<p><p>Number of VMs in the Virtual Network |`ExpressRouteGatewayNumberOfVmInVnet` |Count |Maximum |roleInstance |No|
|Packets received per second<p><p>Total Packets received on ExpressRoute Gateway per second |`ExpressRouteGatewayPacketsPerSecond` |CountPerSecond |Average |roleInstance |No|
|Tunnel MMSA Count<p><p>MMSA Count |`MmsaCount` |Count |Total |ConnectionName, RemoteIP, Instance |Yes|
|Gateway P2S Bandwidth<p><p>Point-to-site bandwidth of a gateway in bytes per second |`P2SBandwidth` |BytesPerSecond |Average |Instance |Yes|
|P2S Connection Count<p><p>Point-to-site connection count of a gateway |`P2SConnectionCount` |Count |Total |Protocol, Instance |Yes|
|Tunnel QMSA Count<p><p>QMSA Count |`QmsaCount` |Count |Total |ConnectionName, RemoteIP, Instance |Yes|
|Tunnel Bandwidth<p><p>Average bandwidth of a tunnel in bytes per second |`TunnelAverageBandwidth` |BytesPerSecond |Average |ConnectionName, RemoteIP, Instance |Yes|
|Tunnel Egress Bytes<p><p>Outgoing bytes of a tunnel |`TunnelEgressBytes` |Bytes |Total |ConnectionName, RemoteIP, Instance |Yes|
|Tunnel Egress Packet Drop Count<p><p>Count of outgoing packets dropped by tunnel |`TunnelEgressPacketDropCount` |Count |Total |ConnectionName, RemoteIP, Instance |Yes|
|Tunnel Egress TS Mismatch Packet Drop<p><p>Outgoing packet drop count from traffic selector mismatch of a tunnel |`TunnelEgressPacketDropTSMismatch` |Count |Total |ConnectionName, RemoteIP, Instance |Yes|
|Tunnel Egress Packets<p><p>Outgoing packet count of a tunnel |`TunnelEgressPackets` |Count |Total |ConnectionName, RemoteIP, Instance |Yes|
|Tunnel Ingress Bytes<p><p>Incoming bytes of a tunnel |`TunnelIngressBytes` |Bytes |Total |ConnectionName, RemoteIP, Instance |Yes|
|Tunnel Ingress Packet Drop Count<p><p>Count of incoming packets dropped by tunnel |`TunnelIngressPacketDropCount` |Count |Total |ConnectionName, RemoteIP, Instance |Yes|
|Tunnel Ingress TS Mismatch Packet Drop<p><p>Incoming packet drop count from traffic selector mismatch of a tunnel |`TunnelIngressPacketDropTSMismatch` |Count |Total |ConnectionName, RemoteIP, Instance |Yes|
|Tunnel Ingress Packets<p><p>Incoming packet count of a tunnel |`TunnelIngressPackets` |Count |Total |ConnectionName, RemoteIP, Instance |Yes|
|Tunnel NAT Allocations<p><p>Count of allocations for a NAT rule on a tunnel |`TunnelNatAllocations` |Count |Total |NatRule, ConnectionName, RemoteIP, Instance |No|
|Tunnel NATed Bytes<p><p>Number of bytes that were NATed on a tunnel by a NAT rule |`TunnelNatedBytes` |Bytes |Total |NatRule, ConnectionName, RemoteIP, Instance |No|
|Tunnel NATed Packets<p><p>Number of packets that were NATed on a tunnel by a NAT rule |`TunnelNatedPackets` |Count |Total |NatRule, ConnectionName, RemoteIP, Instance |No|
|Tunnel NAT Flows<p><p>Number of NAT flows on a tunnel by flow type and NAT rule |`TunnelNatFlowCount` |Count |Total |NatRule, FlowType, ConnectionName, RemoteIP, Instance |No|
|Tunnel NAT Packet Drops<p><p>Number of NATed packets on a tunnel that dropped by drop type and NAT rule |`TunnelNatPacketDrop` |Count |Total |NatRule, DropType, ConnectionName, RemoteIP, Instance |No|
|Tunnel Peak PPS<p><p>Tunnel Peak Packets Per Second |`TunnelPeakPackets` |Count |Maximum |ConnectionName, RemoteIP, Instance |Yes|
|Tunnel Reverse NATed Bytes<p><p>Number of bytes that were reverse NATed on a tunnel by a NAT rule |`TunnelReverseNatedBytes` |Bytes |Total |NatRule, ConnectionName, RemoteIP, Instance |No|
|Tunnel Reverse NATed Packets<p><p>Number of packets on a tunnel that were reverse NATed by a NAT rule |`TunnelReverseNatedPackets` |Count |Total |NatRule, ConnectionName, RemoteIP, Instance |No|
|Tunnel Total Flow Count<p><p>Total flow count on a tunnel |`TunnelTotalFlowCount` |Count |Total |ConnectionName, RemoteIP, Instance |Yes|
|User Vpn Route Count<p><p>Count of P2S User Vpn routes learned by gateway |`UserVpnRouteCount` |Count |Total |RouteType, Instance |No|
|VNet Address Prefix Count<p><p>Count of Vnet address prefixes behind gateway |`VnetAddressPrefixCount` |Count |Total |Instance |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->