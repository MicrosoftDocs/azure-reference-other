---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/29/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: NTANetAnalytics
---


| Column | Type | Description |
|---|---|---|
| AclGroup | string | Access control list group refers to the network security group associated with the network security group rule name (or) the network group associated with the security admin configuration which allowed or denied the connection. |
| AclRule | string | Access control list rule refers to the network security group rule name or the security admin rule name which allowed or denied the connection. |
| AllowedInFlows | long | Count of inbound flows that were allowed. This represents the number of flows that shared the same four-tuple inbound to the network interface at which the flow was captured. |
| AllowedOutFlows | long | Count of outbound flows that were allowed(Outbound to the network interface at which the flow was captured). |
| AzureRegion | string | Azure region locations. |
| _BilledSize | real | The record size in bytes |
| BytesDestToSrc | long | Represents bytes sent from the destination to the source of the flow. |
| BytesSrcToDest | long | Represents bytes sent from the source to the destination of the flow. |
| CompletedFlows | long | This is populated with non-zero value when a flow gets a Completed event. |
| ConnectingVnets | string | Space separated list of virtual network names. |
| ConnectionName | string | Connection Name. |
| ConnectionType | string | Type of the connection. Possible values are VNetPeering, VpnGateway, and ExpressRoute. |
| Country | string | Two letter country code (ISO 3166-1 alpha-2). |
| DeniedInFlows | long | Count of inbound flows that were denied(Inbound to the network interface at which the flow was captured). |
| DeniedOutFlows | long | Count of outbound flows that were denied(Outbound to the network interface at which the flow was captured). |
| DestApplicationGateway | string | Application gateway associated with the destination IP in the flow. |
| DestExpressRouteCircuit | string | Express route circuit associated with the destination IP in the flow. |
| DestIp | string | Destination IP address. |
| DestLoadBalancer | string | Load balancer associated with the destination IP in the flow. |
| DestLocalNetworkGateway | string | Local network gateway associated with the destination IP in the flow. |
| DestNic | string | NIC associated with the destination IP in the flow. |
| DestPort | int | Destination port. |
| DestPublicIps | string | Destination public IP addresses flow information. |
| DestRegion | string | Azure region of virtual network/ network interface/ virtual machine to which the destination IP in the flow belongs to. |
| DestSubnet | string | Subnet associated with the destination IP in the flow. |
| DestSubscription | string | Subscription Id of virtual network/ network interface/ virtual machine to which the destination IP in the flow belongs to. |
| DestVm | string | Virtual machine associated with the destination IP in the flow. |
| ExpressRouteCircuitPeeringType | string | The peering type of the associated express route circuit for the flow. |
| FaSchemaVersion | string | Schema version for ingestion. |
| FlowDirection | string | Direction of the flow which can be inbound or outbound. |
| FlowEncryption | string | The type of flow encryption. |
| FlowEndTime | datetime | Last occurrence of the flow (which will get aggregated) in the flow log processing interval between "FlowIntervalStartTime_t" and "FlowIntervalEndTime_t". In terms of flow log v2, this field contains the time when the last flow with the same four-tuple started (marked as "B" in the raw flow record). |
| FlowIntervalEndTime | datetime | Ending time(in UTC) of the flow log processing interval. |
| FlowIntervalStartTime | datetime | Starting time(in UTC) of the flow log processing interval. This is time from which flow interval is measured. |
| FlowLogResourceId | string | The resource Id for the flow log |
| FlowStartTime | datetime | First occurrence of the flow (which will get aggregated) in the flow log processing interval between "FlowIntervalStartTime_t" and "FlowIntervalEndTime_t". |
| FlowStatus | string | Status of flow which can be allowed or denied. |
| FlowType | string | Category of the flows(allowed values are IntraVNet, InterVNet, S2S, P2S, AzurePublic, ExternalPublic, MaliciousFlow, Unknown Private, Unknown) based on IP addresses involved in flow. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| IsFlowCapturedAtUdrHop | bool | True if flow gets captured at a UDR hop. |
| L4Protocol | string | Transport Protocol,T = TCP, U = UDP. |
| L7Protocol | string | Application Layer protocol name. |
| MacAddress | string | MAC address of the network interface at which the flow was captured. |
| NsgList | string | Network Security Group(NSG) associated with the flow. This is a placeholder for NSG flow logging. |
| NsgRule | string | NSG rule that allowed or denied this flow. This is a placeholder for NSG flow logging. |
| NsgRuleType | string | The type of Network Security Group(NSG) rule used by the flow. This is a placeholder for NSG flow logging. |
| PacketsDestToSrc | long | Represents packets sent from the destination to the source of the flow. |
| PacketsSrcToDest | long | Represents packets sent from the source to the destination of the flow. |
| PrivateEndpointResourceId | string | Resource ID of the private endpoint resource. |
| PrivateLinkResourceId | string | Resource ID of the private link service. |
| PrivateLinkResourceName | string | Resource name of the private link service. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| SrcApplicationGateway | string | Application gateway associated with the source IP in the flow. |
| SrcExpressRouteCircuit | string | Express route circuit associated with the source IP in the flow. |
| SrcIp | string | Source IP address. |
| SrcLoadBalancer | string | Load balancer associated with the source IP in the flow. |
| SrcLocalNetworkGateway | string | Local network gateway associated with the source IP in the flow. |
| SrcNic | string | NIC associated with the source IP in the flow. |
| SrcPublicIps | string | Source public IP addresses flow information. |
| SrcRegion | string | Azure region of virtual network/ network interface/ virtual machine to which the source IP in the flow belongs to. |
| SrcSubnet | string | Subnet associated with the source IP in the flow. |
| SrcSubscription | string | Subscription of the Azure virtual network/ network interface/ virtual machine to which the source IP in the flow belongs to. |
| SrcVm | string | Virtual machine associated with the source IP in the flow. |
| Status | string | Status of the ingestion. Possible values can be Completed, Partial or Failed. |
| SubType | string | Subtype of the ingestion. Values can be Flowlog and StatusMessage. |
| TargetResourceId | string | Target Resource Id for the resource where flow logging has been enabled. |
| TargetResourceType | string | Target Resource Type where flow logging is enabled. It can be virtual network(VNET)/subnet(SUBNET)/network interface(NIC). |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The time when the data gets ingested into the log analytics workspace. |
| TimeProcessed | datetime | Time(in UTC) at which the traffic analytics processed the raw flow logs from the storage account. |
| Type | string | The name of the table |
