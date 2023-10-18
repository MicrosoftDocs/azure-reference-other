---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: microsoft.network/vpngateways, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Gateway S2S Bandwidth**<p><p>Site-to-site bandwidth of a gateway in bytes per second |`AverageBandwidth` |BytesPerSecond |Average |`Instance`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**BGP Peer Status**<p><p>Status of BGP peer |`BgpPeerStatus` |Count |Average |`BgpPeerAddress`, `Instance`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|
|**BGP Routes Advertised**<p><p>Count of Bgp Routes Advertised through tunnel |`BgpRoutesAdvertised` |Count |Total |`BgpPeerAddress`, `Instance`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**BGP Routes Learned**<p><p>Count of Bgp Routes Learned through tunnel |`BgpRoutesLearned` |Count |Total |`BgpPeerAddress`, `Instance`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Tunnel MMSA Count**<p><p>MMSA Count |`MmsaCount` |Count |Total |`ConnectionName`, `RemoteIP`, `Instance`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Tunnel QMSA Count**<p><p>QMSA Count |`QmsaCount` |Count |Total |`ConnectionName`, `RemoteIP`, `Instance`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Tunnel Bandwidth**<p><p>Average bandwidth of a tunnel in bytes per second |`TunnelAverageBandwidth` |BytesPerSecond |Average |`ConnectionName`, `RemoteIP`, `Instance`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Tunnel Egress Bytes**<p><p>Outgoing bytes of a tunnel |`TunnelEgressBytes` |Bytes |Total |`ConnectionName`, `RemoteIP`, `Instance`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Tunnel Egress Packet Drop Count**<p><p>Count of outgoing packets dropped by tunnel |`TunnelEgressPacketDropCount` |Count |Total |`ConnectionName`, `RemoteIP`, `Instance`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Tunnel Egress TS Mismatch Packet Drop**<p><p>Outgoing packet drop count from traffic selector mismatch of a tunnel |`TunnelEgressPacketDropTSMismatch` |Count |Total |`ConnectionName`, `RemoteIP`, `Instance`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Tunnel Egress Packets**<p><p>Outgoing packet count of a tunnel |`TunnelEgressPackets` |Count |Total |`ConnectionName`, `RemoteIP`, `Instance`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Tunnel Ingress Bytes**<p><p>Incoming bytes of a tunnel |`TunnelIngressBytes` |Bytes |Total |`ConnectionName`, `RemoteIP`, `Instance`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Tunnel Ingress Packet Drop Count**<p><p>Count of incoming packets dropped by tunnel |`TunnelIngressPacketDropCount` |Count |Total |`ConnectionName`, `RemoteIP`, `Instance`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Tunnel Ingress TS Mismatch Packet Drop**<p><p>Incoming packet drop count from traffic selector mismatch of a tunnel |`TunnelIngressPacketDropTSMismatch` |Count |Total |`ConnectionName`, `RemoteIP`, `Instance`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Tunnel Ingress Packets**<p><p>Incoming packet count of a tunnel |`TunnelIngressPackets` |Count |Total |`ConnectionName`, `RemoteIP`, `Instance`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Tunnel NAT Allocations**<p><p>Count of allocations for a NAT rule on a tunnel |`TunnelNatAllocations` |Count |Total |`NatRule`, `ConnectionName`, `RemoteIP`, `Instance`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|
|**Tunnel NATed Bytes**<p><p>Number of bytes that were NATed on a tunnel by a NAT rule |`TunnelNatedBytes` |Bytes |Total |`NatRule`, `ConnectionName`, `RemoteIP`, `Instance`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|
|**Tunnel NATed Packets**<p><p>Number of packets that were NATed on a tunnel by a NAT rule |`TunnelNatedPackets` |Count |Total |`NatRule`, `ConnectionName`, `RemoteIP`, `Instance`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|
|**Tunnel NAT Flows**<p><p>Number of NAT flows on a tunnel by flow type and NAT rule |`TunnelNatFlowCount` |Count |Total |`NatRule`, `FlowType`, `ConnectionName`, `RemoteIP`, `Instance`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|
|**Tunnel NAT Packet Drops**<p><p>Number of NATed packets on a tunnel that dropped by drop type and NAT rule |`TunnelNatPacketDrop` |Count |Total |`NatRule`, `DropType`, `ConnectionName`, `RemoteIP`, `Instance`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|
|**Tunnel Peak PPS**<p><p>Tunnel Peak Packets Per Second |`TunnelPeakPackets` |Count |Maximum |`ConnectionName`, `RemoteIP`, `Instance`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Tunnel Reverse NATed Bytes**<p><p>Number of bytes that were reverse NATed on a tunnel by a NAT rule |`TunnelReverseNatedBytes` |Bytes |Total |`NatRule`, `ConnectionName`, `RemoteIP`, `Instance`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|
|**Tunnel Reverse NATed Packets**<p><p>Number of packets on a tunnel that were reverse NATed by a NAT rule |`TunnelReverseNatedPackets` |Count |Total |`NatRule`, `ConnectionName`, `RemoteIP`, `Instance`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|
|**Tunnel Total Flow Count**<p><p>Total flow count on a tunnel |`TunnelTotalFlowCount` |Count |Total |`ConnectionName`, `RemoteIP`, `Instance`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**VNet Address Prefix Count**<p><p>Count of Vnet address prefixes behind gateway |`VnetAddressPrefixCount` |Count |Total |`Instance`|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|