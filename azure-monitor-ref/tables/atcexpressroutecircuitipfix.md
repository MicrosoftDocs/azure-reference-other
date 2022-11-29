---
title: Azure Monitor Logs reference - ATCExpressRouteCircuitIpfix
description: Reference for ATCExpressRouteCircuitIpfix table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# ATCExpressRouteCircuitIpfix

 This table has Express Route Circuit IPFIX flow records. Flow records are captured and emitted by Azure Traffic Collector (ATC).

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Azure Traffic Collector




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ATCRegion | string | Azure Traffic Collector (ATC) deployment region. |
| ATCResourceId | string | Azure resource ID of Azure Traffic Collector (ATC). |
| BgpNextHop | string | Border Gateway Protocol (BGP) next hop as defined in the routing table. |
| DestinationIp | string | Destination IP address. |
| DestinationPort | int | TCP destination port. |
| Dot1qCustomerVlanId | int | Dot1q Customer VlanId. |
| Dot1qVlanId | int | Dot1q VlanId. |
| DstAsn | int | Destination Autonomous System Number (ASN). |
| DstMask | int | Mask of destination subnet. |
| DstSubnet | string | Destination subnet of destination IP. |
| ExRCircuitDirectPortId | string | Azure resource ID of Express Route Circuit's direct port. |
| ExRCircuitId | string | Azure resource ID of Express Route Circuit. |
| ExRCircuitServiceKey | string | Service key of Express Route Circuit. |
| FlowRecordTime | datetime | Timestamp (UTC) when Express Route Circuit emitted this flow record. |
| Flowsequence | long | Flow sequence of this flow. |
| IcmpType | int | Protocol type as specified in IP header. |
| IpClassOfService | int | IP Class of service as specified in IP header. |
| IpProtocolIdentifier | int | Protocol type as specified in IP header. |
| IpVerCode | int | IP version as defined in the IP header. |
| MaxTtl | int | Maximum time to live (TTL) as defined in the IP header. |
| MinTtl | int | Minimum time to live (TTL) as defined in the IP header. |
| NextHop | string | Next hop as per forwarding table. |
| NumberOfBytes | long | Total number of bytes of packets captured in this flow. |
| NumberOfPackets | long | Total number of packets captured in this flow. |
| OperationName | string | The specific Azure Traffic Collector (ATC) operation that emitted this flow record. |
| PeeringType | string | Express Route Circuit peering type. |
| Protocol | int | Protocol type as specified in IP header. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SchemaVersion | string | Flow record schema version. |
| SourceIp | string | Source IP address. |
| SourcePort | int | TCP source port. |
| SourceSystem | string |  |
| SrcAsn | int | Source Autonomous System Number (ASN). |
| SrcMask | int | Mask of source subnet. |
| SrcSubnet | string | Source subnet of source IP. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TcpFlag | int | TCP flag as defined in the TCP header. |
| TenantId | string |  |
| TimeGenerated | datetime | Timestamp (UTC) when the Azure Traffic Collector (ATC) emitted this flow record. |
| Type | string | The name of the table |
