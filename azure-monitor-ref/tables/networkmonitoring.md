---
title: Azure Monitor Logs reference - NetworkMonitoring
description: Reference for NetworkMonitoring table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# NetworkMonitoring

 

## Categories

- Network
## Solutions

- Network Performance Monitor




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AddressType | string |  |
| AgentCapability | int |  |
| AgentFqdn | string |  |
| AgentId | string |  |
| AgentIP | string |  |
| AlertsCount | int |  |
| AvgHopLatencyList | string |  |
| AzureHopListDiagnosticCode | string |  |
| AzureHopListHealth | string |  |
| AzureHopListIPAddress | string |  |
| AzureHopListResourceID | string |  |
| AzureHopListType | string |  |
| BitsInPerSecond | long |  |
| BitsOutPerSecond | long |  |
| CircuitName | string |  |
| CircuitRegion | string |  |
| CircuitResourceGroup | string |  |
| CircuitResourceId | string |  |
| CircuitSKUFamily | string |  |
| CircuitSKUTier | string |  |
| CircuitSubscriptionId | string |  |
| Computer | string |  |
| ConnectionMonitorResourceId | string |  |
| ConnectionResourceId | string |  |
| CustomFieldName | string |  |
| CustomFieldValueFloat | long |  |
| CustomFieldValueHex | string |  |
| CustomFieldValueInt | long |  |
| CustomFieldValueString | string |  |
| CustomMonitoringData | string |  |
| CustomOid | string |  |
| CustomOidResponseSuffix | string |  |
| DestinationNetwork | string |  |
| DestinationNetworkNodeInterface | string |  |
| DestinationNetworkNodeLink | string |  |
| DestinationSubNetwork | string |  |
| Details | string |  |
| DeviceComponentType | string |  |
| DeviceMonitoringChannel | string |  |
| DeviceState | string |  |
| DeviceType | string |  |
| DiagnosticHop | string |  |
| DiagnosticHopLatency | string |  |
| DiskCount | int |  |
| EgressByteCount | long |  |
| EgressPacketCount | long |  |
| EndpointId | int |  |
| Enterprise | string |  |
| ExporterIp | string |  |
| ExportProtocol | string |  |
| FanCount | int |  |
| FriendlyName | string |  |
| GenTrapType | string |  |
| HighLatency | real |  |
| HostFqdn | string |  |
| HostFqdn1 | string |  |
| HostFqdn2 | string |  |
| HostIp | string |  |
| HostIp1 | string |  |
| HostIp2 | string |  |
| IcmpPingStatus | string |  |
| ifAdminStatus | string |  |
| ifHCInBroadcastPkts | long |  |
| ifHCInMulticastPkts | long |  |
| ifHCInOctets | long |  |
| ifHCInUcastPkts | long |  |
| ifHCOutBroadcastPkts | long |  |
| ifHCOutMulticastPkts | long |  |
| ifHCOutOctetsMib2 | int |  |
| ifHCOutUcastPkts | long |  |
| ifHighSpeed | long |  |
| ifInDiscardsMib2 | long |  |
| ifInErrors | long |  |
| ifMtu | long |  |
| ifOperStatus | string |  |
| ifOutDiscards | long |  |
| ifOutErrors | long |  |
| ifOutQLen | long |  |
| ifPhysAddress | string |  |
| ifType | string |  |
| InBroadCastPktsPerSec | long |  |
| Index | long |  |
| InDiscardsPercent | int |  |
| InDiscardsPerSec | long |  |
| InErrorsPercent | int |  |
| InErrorsPerSec | long |  |
| IngressByteCount | long |  |
| IngressPacketCount | long |  |
| InMultiCastPktsPerSec | long |  |
| InOctetsPerSec | long |  |
| InterfaceCount | int |  |
| InterfaceId | int |  |
| InternalByteCount | long |  |
| InternalPacketCount | long |  |
| InUnicastPktsPerSec | long |  |
| IpV4Addresses | string |  |
| IpV4Subnets | string |  |
| IpV6Addresses | string |  |
| IpV6Subnets | string |  |
| IsPrimary | bool |  |
| L2ConnectedNodes | string |  |
| L2ConnectedPorts | string |  |
| L4Port | int |  |
| L4Protocol | string |  |
| L7Protocol | string |  |
| LatencyBenchmark | real |  |
| LatencyFaultLinks | string |  |
| LatencyHealthIndicator | bool |  |
| LatencyHealthState | string |  |
| LatencyMode | string |  |
| LatencyThreshold | real |  |
| LatencyThresholdMode | string |  |
| Loss | real |  |
| LossBenchmark | real |  |
| LossFaultLinks | string |  |
| LossHealthIndicator | bool |  |
| LossHealthState | string |  |
| LossMode | string |  |
| LossThreshold | real |  |
| LossThresholdMode | string |  |
| LowLatency | real |  |
| MachineType | int |  |
| MaxHopLatencyList | string |  |
| MedianLatency | real |  |
| MemAvailablePercent | int |  |
| MemCount | int |  |
| MemTotalInMB | long |  |
| MessageCode | string |  |
| MessageDetails | string |  |
| MessageType | string |  |
| MicrosoftEdge | string |  |
| MicrosoftEdgeAlias | string |  |
| MinHopLatencyList | string |  |
| Model | string |  |
| NodeLinkCount | int |  |
| NodeUniqueName | string |  |
| NotificationCode | int |  |
| NotificationType | string |  |
| NPMAgentEnvironment | string |  |
| OSType | string |  |
| OutBroadCastPktsPerSec | long |  |
| OutDiscardsPercent | int |  |
| OutDiscardsPerSec | long |  |
| OutErrorsPercent | long |  |
| OutErrorsPerSec | long |  |
| OutMultiCastPktsPerSec | long |  |
| OutOctetsPerSec | long |  |
| OutUnicastPktsPerSec | long |  |
| Path | string |  |
| PathInformation | string |  |
| PeeringLocation | string |  |
| PeeringName | string |  |
| PeeringType | string |  |
| PingDelayInMsec | real |  |
| Port | int |  |
| PortName | string |  |
| PrefixLength | string |  |
| PrimaryBytesInPerSecond | long |  |
| PrimaryBytesOutPerSecond | long |  |
| ProcessorCount | int |  |
| ProcessorTimePercent | int |  |
| Protocol | string |  |
| ProviderEdge | string |  |
| ProviderEdgeAlias | string |  |
| ProvisioningState | string |  |
| ResponseCodeHealthState | string |  |
| RouteDestination | string |  |
| RouteMetric | string |  |
| RouteNextHop | string |  |
| RouterIP | string |  |
| RouterName | string |  |
| RouteTableIpV4NextHops | string |  |
| RouteTableIpV6NextHops | string |  |
| RouteTableNextHopNodes | string |  |
| RuleName | string |  |
| SecondaryBytesInPerSecond | long |  |
| SecondaryBytesOutPerSecond | long |  |
| ServiceKey | string |  |
| ServiceLossHealthState | string |  |
| ServiceLossPercent | real |  |
| ServiceProvider | string |  |
| ServiceResponseCode | long |  |
| ServiceResponseHealthState | string |  |
| ServiceResponseThreshold | real |  |
| ServiceResponseThresholdMode | string |  |
| ServiceResponseTime | real |  |
| ServiceTestId | int |  |
| SnmpManagementIpV4Address | string |  |
| SnmpManagementIpV6Address | string |  |
| SnmpPingStatus | string |  |
| SnmpVersion | string |  |
| SourceNetwork | string |  |
| SourceNetworkNodeInterface | string |  |
| SourceNetworkNodeLink | string |  |
| SourceSubNetwork | string |  |
| SourceSystem | string |  |
| SpecificTrapType | string |  |
| SubnetId | string |  |
| SubnetId1 | string |  |
| SubnetId2 | string |  |
| SubnetLinkCount | int |  |
| SubscriptionId | string |  |
| SubType | string |  |
| SupportsSnmp | bool |  |
| sysContact | string |  |
| sysDescr | string |  |
| sysLocation | string |  |
| sysName | string |  |
| sysObjectID | string |  |
| sysUpTime | long |  |
| Target | string |  |
| TestName | string |  |
| TimeGenerated | datetime |  |
| TimeProcessed | datetime |  |
| TimeSinceActive | int |  |
| ToS | int |  |
| TotalByteCount | long |  |
| TotalFlowRecords | long |  |
| TotalPacketCount | long |  |
| TotalPeerings | int |  |
| TotalSessions | int |  |
| TraceRouteCompletionTime | datetime |  |
| TrapCollectionIntervalInSeconds | int |  |
| TrapCount | int |  |
| TrapData | string |  |
| TrapOid | string |  |
| Type | string | The name of the table |
| UtilizationHealthState | string |  |
| Vendor | string |  |
| VirtualNetwork | string |  |
| VLan | int |  |
