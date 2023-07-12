---
title: Supported metrics - Microsoft.ManagedNetworkFabric/networkDevices
description: Reference for Microsoft.ManagedNetworkFabric/networkDevices metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.ManagedNetworkFabric/networkDevices  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.ManagedNetworkFabric/networkDevices resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Acl Matched Packets<p><p>Count of the number of packets matching the current ACL entry. |`AclMatchedPackets` |Count |Average |FabricId, AclSetName, AclEntrySequenceId, AclSetType |Yes|
|BGP Peer Status<p><p>Operational state of the BGP peer. State is represented in numerical form. Idle : 1, Connect : 2, Active : 3, Opensent : 4, Openconfirm : 5, Established : 6 |`BgpPeerStatus` |Unspecified |Minimum |FabricId, IpAddress |Yes|
|Component Operational State<p><p>The current operational status of the component. |`ComponentOperStatus` |Unspecified |Minimum |FabricId, ComponentName |Yes|
|Cpu Utilization Max<p><p>Max cpu utilization. The maximum value of the percentage measure of the statistic over the time interval. |`CpuUtilizationMax` |Percent |Average |FabricId, ComponentName |Yes|
|Cpu Utilization Min<p><p>Min cpu utilization. The minimum value of the percentage measure of the statistic over the time interval. |`CpuUtilizationMin` |Percent |Average |FabricId, ComponentName |Yes|
|Fan Speed<p><p>Current fan speed. |`FanSpeed` |Unspecified |Average |FabricId, ComponentName |Yes|
|Ethernet Interface In CRC Errors<p><p>The total number of frames received that had a length (excluding framing bits, but including FCS octets) of between 64 and 1518 octets, inclusive, but had either a bad Frame Check Sequence (FCS) with an integral number of octets (FCS Error) or a bad FCS with a non-integral number of octets (Alignment Error) |`IfEthInCrcErrors` |Count |Average |FabricId, InterfaceName |Yes|
|Ethernet Interface In Fragment Frames<p><p>The total number of frames received that were less than 64 octets in length (excluding framing bits but including FCS octets) and had either a bad Frame Check Sequence (FCS) with an integral number of octets (FCS Error) or a bad FCS with a non-integral number of octets (Alignment Error). |`IfEthInFragmentFrames` |Count |Average |FabricId, InterfaceName |Yes|
|Ethernet Interface In Jabber Frames<p><p>Number of jabber frames received on the interface. Jabber frames are typically defined as oversize frames which also have a bad CRC. |`IfEthInJabberFrames` |Count |Average |FabricId, InterfaceName |Yes|
|Ethernet Interface In MAC Control Frames<p><p>MAC layer control frames received on the interface |`IfEthInMacControlFrames` |Count |Average |FabricId, InterfaceName |Yes|
|Ethernet Interface In MAC Pause Frames<p><p>MAC layer PAUSE frames received on the interface |`IfEthInMacPauseFrames` |Count |Average |FabricId, InterfaceName |Yes|
|Ethernet Interface In Maxsize Exceeded<p><p>The total number frames received that are well-formed dropped due to exceeding the maximum frame size on the interface. |`IfEthInMaxsizeExceeded` |Count |Average |FabricId, InterfaceName |Yes|
|Ethernet Interface In Oversize Frames<p><p>The total number of frames received that were longer than 1518 octets (excluding framing bits, but including FCS octets) and were otherwise well formed. |`IfEthInOversizeFrames` |Count |Average |FabricId, InterfaceName |Yes|
|Ethernet Interface Out MAC Control Frames<p><p>MAC layer control frames sent on the interface. |`IfEthOutMacControlFrames` |Count |Average |FabricId, InterfaceName |Yes|
|Ethernet Interface Out MAC Pause Frames<p><p>MAC layer PAUSE frames sent on the interface. |`IfEthOutMacPauseFrames` |Count |Average |FabricId, InterfaceName |Yes|
|Interface In Broadcast Pkts<p><p>The number of packets, delivered by this sub-layer to a higher (sub-)layer, that were addressed to a broadcast address at this sub-layer. |`IfInBroadcastPkts` |Count |Average |FabricId, InterfaceName |Yes|
|Interface In Discards<p><p>The number of inbound packets that were chosen to be discarded even though no errors had been detected to prevent their being deliverable to a higher-layer protocol. |`IfInDiscards` |Count |Average |FabricId, InterfaceName |Yes|
|Interface In Errors<p><p>For packet-oriented interfaces, the number of inbound packets that contained errors preventing them from being deliverable to a higher-layer protocol. |`IfInErrors` |Count |Average |FabricId, InterfaceName |Yes|
|Interface In FCS Errors<p><p>Number of received packets which had errors in the frame check sequence (FCS), i.e., framing errors. |`IfInFcsErrors` |Count |Average |FabricId, InterfaceName |Yes|
|Interface In Multicast Pkts<p><p>The number of packets, delivered by this sub-layer to a higher (sub-)layer, that were addressed to a multicast address at this sub-layer. For a MAC-layer protocol, this includes both Group and Functional addresses. |`IfInMulticastPkts` |Count |Average |FabricId, InterfaceName |Yes|
|Interface In Octets<p><p>The total number of octets received on the interface, including framing characters. |`IfInOctets` |Count |Average |FabricId, InterfaceName |Yes|
|Interface In Pkts<p><p>The total number of packets received on the interface, including all unicast, multicast, broadcast and bad packets etc. |`IfInPkts` |Count |Average |FabricId, InterfaceName |Yes|
|Interface In Unicast Pkts<p><p>The number of packets, delivered by this sub-layer to a higher (sub-)layer, that were not addressed to a multicast or broadcast address at this sub-layer. |`IfInUnicastPkts` |Count |Average |FabricId, InterfaceName |Yes|
|Interface Out Broadcast Pkts<p><p>The total number of packets that higher-level protocols requested be transmitted, and that were addressed to a broadcast address at this sub-layer, including those that were discarded or not sent. |`IfOutBroadcastPkts` |Count |Average |FabricId, InterfaceName |Yes|
|Interface Out Discards<p><p>The number of outbound packets that were chosen to be discarded even though no errors had been detected to prevent their being transmitted. |`IfOutDiscards` |Count |Average |FabricId, InterfaceName |Yes|
|Interface Out Errors<p><p>For packet-oriented interfaces, the number of outbound packets that could not be transmitted because of errors. |`IfOutErrors` |Count |Average |FabricId, InterfaceName |Yes|
|Interface Out Multicast Pkts<p><p>The total number of packets that higher-level protocols requested be transmitted, and that were addressed to a multicast address at this sub-layer, including those that were discarded or not sent. For a MAC-layer protocol, this includes both Group and Functional addresses. |`IfOutMulticastPkts` |Count |Average |FabricId, InterfaceName |Yes|
|Interface Out Octets<p><p>The total number of octets transmitted out of the interface, including framing characters. |`IfOutOctets` |Count |Average |FabricId, InterfaceName |Yes|
|Interface Out Pkts<p><p>The total number of packets transmitted out of the interface, including all unicast, multicast, broadcast, and bad packets etc. |`IfOutPkts` |Count |Average |FabricId, InterfaceName |Yes|
|Interface Out Unicast Pkts<p><p>The total number of packets that higher-level requested be transmitted, and that were not addressed to a multicast or broadcast address at this sub-layer, including those that were discarded or not sent. |`IfOutUnicastPkts` |Count |Average |FabricId, InterfaceName |Yes|
|Interface Operational State<p><p>The current operational state of the interface. State is represented in numerical form. Up: 0, Down: 1, Lower_layer_down: 2, Testing: 3, Unknown: 4, Dormant: 5, Not_present: 6. |`InterfaceOperStatus` |Unspecified |Minimum |FabricId, InterfaceName |Yes|
|Lacp Errors<p><p>Number of LACPDU illegal packet errors. |`LacpErrors` |Count |Average |FabricId, InterfaceName |Yes|
|Lacp In Pkts<p><p>Number of LACPDUs received. |`LacpInPkts` |Count |Average |FabricId, InterfaceName |Yes|
|Lacp Out Pkts<p><p>Number of LACPDUs transmitted. |`LacpOutPkts` |Count |Average |FabricId, InterfaceName |Yes|
|Lacp Rx Errors<p><p>Number of LACPDU receive packet errors. |`LacpRxErrors` |Count |Average |FabricId, InterfaceName |Yes|
|Lacp Tx Errors<p><p>Number of LACPDU transmit packet errors. |`LacpTxErrors` |Count |Average |FabricId, InterfaceName |Yes|
|Lacp Unknown Errors<p><p>Number of LACPDU unknown packet errors. |`LacpUnknownErrors` |Count |Average |FabricId, InterfaceName |Yes|
|Lldp Frame In<p><p>The number of lldp frames received. |`LldpFrameIn` |Count |Average |FabricId, InterfaceName |Yes|
|Lldp Frame Out<p><p>The number of frames transmitted out. |`LldpFrameOut` |Count |Average |FabricId, InterfaceName |Yes|
|Lldp Tlv Unknown<p><p>The number of frames received with unknown TLV. |`LldpTlvUnknown` |Count |Average |FabricId, InterfaceName |Yes|
|Memory Available<p><p>The available memory physically installed, or logically allocated to the component. |`MemoryAvailable` |Bytes |Average |FabricId, ComponentName |Yes|
|Memory Utilized<p><p>The memory currently in use by processes running on the component, not considering reserved memory that is not available for use. |`MemoryUtilized` |Bytes |Average |FabricId, ComponentName |Yes|
|Power Supply Maximum Power Capacity<p><p>Maximum power capacity of the power supply (watts). |`PowerSupplyCapacity` |Unspecified |Average |FabricId, ComponentName |Yes|
|Power Supply Input Current<p><p>The input current draw of the power supply (amps). |`PowerSupplyInputCurrent` |Unspecified |Average |FabricId, ComponentName |Yes|
|Power Supply Input Voltage<p><p>Input voltage to the power supply (volts). |`PowerSupplyInputVoltage` |Unspecified |Average |FabricId, ComponentName |Yes|
|Power Supply Output Current<p><p>The output current supplied by the power supply (amps) |`PowerSupplyOutputCurrent` |Unspecified |Average |FabricId, ComponentName |Yes|
|Power Supply Output Power<p><p>Output power supplied by the power supply (watts) |`PowerSupplyOutputPower` |Unspecified |Average |FabricId, ComponentName |Yes|
|Power Supply Output Voltage<p><p>Output voltage supplied by the power supply (volts). |`PowerSupplyOutputVoltage` |Unspecified |Average |FabricId, ComponentName |Yes|
|Temperature Max<p><p>Max temperature in degrees Celsius of the component. The maximum value of the statistic over the sampling period. |`TemperatureMax` |Unspecified |Average |FabricId, ComponentName |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->