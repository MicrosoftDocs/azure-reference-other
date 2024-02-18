---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: NTATopologyDetails
---


| Column | Type | Description |
|---|---|---|
| Access | string | Access(Allow/Deny) associated with network security group rule. |
| AddressPrefixes | string | The address prefixes associated with the discovered resource. |
| AllowForwardedTraffic | bool | Whether the forwarded traffic from the VMs in the local virtual network will be allowed/disallowed in remote virtual network. |
| AllowGatewayTransit | bool | If gateway links can be used in remote virtual networking to link to this virtual network. |
| AllowVirtualNetworkAccess | bool | Whether the VMs in the local virtual network space would be able to access the VMs in remote virtual network space. |
| AppGatewayType | string | Type of the application gateway resource. This would be either internal or internet facing. |
| ApplicationGatewayBackendPools | string | Pool of application gateway backend IP addresses. |
| AzureAsn | long | The Azure ASN of express route circuit peering. |
| AzureResourceType | string | Resource type of the discovered resource. |
| BackendAddressPool | string | The reference to backend address pool resource. |
| BackendIpAddress | string | Backend IP address associated with the inbound NAT rules. |
| BackendPort | int | Backend port associated with the inbound NAT rules. The port used for the internal endpoint. Acceptable values range from 1 to 65535. |
| BackendSubnets | string | List of space separated subnets associated with the discovered resource. |
| BgpEnabled | bool | Whether BGP is enabled for this resource or not. |
| _BilledSize | real | The record size in bytes |
| CircuitProvisioningState | string | The current provisioning state of express route circuit. |
| ComponentType | string | Component type of the status message. Possible values are Flowlog/Topology. |
| ConnectionStatus | string | Gateway connection status. |
| ConnectionType | string | Connection type of the discovered connection. |
| Description | string | Description of with network security group rule. |
| DestinationAddressPrefix | string | Destination address prefix associated with network security group rule. |
| DestinationPortRange | string | Destination port range associated with network security group rule. |
| Direction | string | Direction associated with network security group rule. |
| DiscoveryRegion | string | The region where resource is discovered. |
| EgressBytesTransferred | long | The egress bytes transferred in this connection. |
| EnableIpForwarding | bool | Indicates whether IP forwarding is enabled on the network interface. |
| EncryptionEnabled | bool | Indicates whether encryption is enabled on the virtual network. |
| EncryptionEnforcement | string | Indicates whether the encrypted virtual network allows VM that does not support encryption. Possible values include DropUnencrypted/AllowUnencrypted. |
| FloatingIpEnabled | bool | Configures a virtual machine's endpoint for the floating IP capability required to configure a SQL AlwaysOn Availability Group. This setting is required when using the SQL AlwaysOn Availability Groups in SQL server. This setting can't be changed after you create the endpoint. |
| FlowLogStorageAccount | string | Id of the storage account which is used to store the flow log. |
| FrontendIpAddress | string | Frontend IP address associated with the inbound NAT rule. |
| FrontendIps | string | Frontend IP address of the load balancer. |
| FrontendPort | int | Frontend port associated with the inbound NAT rules. The port for the external endpoint. Port numbers for each rule must be unique within the Load Balancer. Acceptable values range from 1 to 65534. |
| FrontendSubnet | string | The subnet of the discovered load balancer resource. This will be populated when the load balancer is internal load balancer. |
| FrontendSubnets | string | List of space separated subnets of the discovered load balancer resource. This will be populated when the load balancer is internal load balancer. |
| GatewayConnectionType | string | Gateway connection type. |
| GatewaySubnet | string | Subnet associated with the application aateway resource. |
| GatewayType | string | Gateway Type assocaited with virtual network gateway, VPN or express route. |
| IngressBytesTransferred | long | The ingress bytes transferred in this connection. |
| IpAddress | string | Gateway IP address of the discovered resource. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| IsFlowEnabled | bool | Flag to enable/disable flow logging. |
| IsVirtualAppliance | bool | Boolean to specify if the discovered resource is a virtual appliance. |
| LoadBalancerBackendPools | string | Pool of load balancer backend IP addresses. |
| LoadBalancerType | string | The type of the discovered load balancer resource. Possible values are internal load balancer or internet facing load balancer. |
| LocalNetworkGateway | string | The reference to local network gateway resource. |
| LocalPreference | string | Local preference value as set with the set local-preference route-map configuration command of the express route circuit route. |
| MacAddress | string | MAC address of the discovered NIC. |
| Name | string | Name of the discovered resource. |
| Network | string | IP address of a network entity associated with the express route circuit route. |
| NextHopIp | string | The IP address packets should be forwarded to. Next hop values are only allowed in routes where the next hop type is virtual appliance. |
| NextHopType | string | The type of azure hop the packet should be sent to. |
| Nsg | string | The reference to the network security group resource. |
| Path | string | Autonomous system paths to the destination network of the express route circuit route. |
| Peer | string | The reference to peerings resource. |
| PeerAsn | long | The peer ASN of express route circuit peering. |
| PeeringType | string | The peering type of express route circuit peering. |
| PrimaryAzurePort | string | The primary port of express route circuit peering. |
| PrimaryBytesIn | long | The primary bytes in of the peering. |
| PrimaryBytesOut | long | The primary bytes out of the peering. |
| PrimaryNextHop | string | Primary next hop address of the express route circuit route. |
| PrimaryPeerAddressPrefix | string | The primary peer address prefix of express route circuit peering. |
| Priority | int | Specifies the priority for the virtual machine. Minimum api-version: 2019-03-01. |
| PrivateEndpointResourceId | string | Resource ID of the private endpoint resource. |
| PrivateFrontendIps | string | Front end private IP addresses associated with the application gateway resource. |
| PrivateIpAddresses | string | Private IP address of the IP configuration. |
| PrivateLinkResourceId | string | Resource ID of the private link service. |
| Protocol | string | Protocol associated with network security group rule. |
| PublicFrontendIps | string | Front end public IP addresses associated with the application gateway resource. |
| PublicIpAddresses | string | Public IP address bound to the IP configuration. |
| Region | string | Region of the discovered resource. |
| RouteTable | string | The reference to the route table resource. |
| RoutingWeight | int | The routing weight. |
| RuleType | string | The type of the network security group rule. |
| SchemaVersion | string | This is topology schema version and not related to flow log schema version. |
| SecondaryAzurePort | string | The secondary port of express route circuit peering. |
| SecondaryBytesIn | long | The secondary bytes in of the peering. |
| SecondaryBytesOut | long | The secondary bytes out of the peering. |
| SecondaryNextHop | string | Secondary next hop address of the express route circuit route. |
| SecondaryPeerAddressPrefix | string | The secondary peer address prefix of express route circuit peering. |
| ServiceProviderProperties | string | "Contains service provider properties in an express route circuit. Service provider properties semicolon seperated "ServiceProviderName;ServiceProviderBandwidthInMbps;ServiceProviderPeeringLocation"". |
| ServiceProviderProvisioningState | string | The service provider provisioning state state of the resource. |
| Sku | string | SKU or pricing associated with the discovered resource. |
| SkuDetail | string | "The SKU of express route circuit. Express route circuit SKU detail semicolon seperated "Family;Name;Tier"". |
| SourceAddressPrefix | string | Source address prefix associated with network security group rule. |
| SourcePortRange | string | Source port range associated with network security group rule. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| State | string | The peering state of express route circuit peering. |
| Status | string | Status of the ingestion. Possible values can be Completed/Partial/Failed. |
| Subnet1 | string | Subnet associated with the discovered subnetwork connection. |
| Subnet2 | string | Subnet associated with the discovered subnetwork connection. |
| SubnetPrefixes | string | Space separated string of address prefixes in local network address space. |
| SubnetRegion1 | string | Subnet region associated with the discovered subnetwork connection. |
| SubnetRegion2 | string | Subnet region associated with the discovered subnetwork connection. |
| Subnetwork | string | The refrence to the subnetwork resource. |
| Subscription | string | Subscription guid of the discovered resource. |
| SubscriptionName | string | Subscription name of the discovered resource. |
| SubType | string | Subtype of the ingestion. Values can be Topology and StatusMessage. |
| Tags | string | Tags associated with the discovered resource. |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The time when the data gets ingested into the log analytics workspace. |
| TimeProcessed | datetime | Time(in UTC) at which the traffic analytics discovered the topology resource. |
| TopologyVersion | string | Topology version. |
| Type | string | The name of the table |
| UseRemoteGateways | bool | If remote gateways can be used on this virtual network. If the flag is set to true, and allowGatewayTransit on remote peering is also true, virtual network will use gateways of remote virtual network for transit. Only one peering can have this flag set to true. This flag cannot be set if virtual network already has a gateway. |
| VipAddress | string | Space separated list of IP addresses associated with virtual network gateway. |
| VirtualAppliances | string | Virtual appliances associated with the discovered subnetwork connection. |
| VirtualMachine | string | The reference to a virtual machine. |
| VirtualNetwork1 | string | The reference to the virtual network resource associated with the virtual network peering. |
| VirtualNetwork2 | string | The reference to the virtual network resource associated with the virtual network peering. |
| VirtualNetworkGateway1 | string | The reference to virtual network gateway resource. |
| VirtualNetworkGateway2 | string | The reference to virtual network gateway resource. |
| VirtualSubnetwork | string | Virtual subnetwork associated with virtual network gateway. |
| VlanId | int | The VLAN Id of the peering. |
| VmssName | string | The virtual machine scale set name. |
| VnetEncryptionSupported | bool | Indicates whether the virtual machine this nic is attached to supports encryption. |
| VpnClientAddressPrefixes | string | The reference to the address prefix resource which represents address prefix for P2S VpnClient. Will be empty when no point to site is configured. |
| Weight | int | Route weight of the express route circuit route. |
| Zones | string | The virtual machine zones information. |
