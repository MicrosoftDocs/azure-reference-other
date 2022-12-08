---
title: Azure Monitor Logs reference - ASimNetworkSessionLogs
description: Reference for ASimNetworkSessionLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/8/2022
---

# ASimNetworkSessionLogs

 The Microsoft Sentinel network session normalization schema represents an IP network activity, such as network connections and network sessions. Such events are reported, for example, by operating systems, routers, firewalls, and intrusion prevention systems.

## Categories

- Security
## Solutions

- Microsoft Sentinel
## Resource types

- Microsoft Sentinel Network Session ASim schema




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AdditionalFields | dynamic | Additional information, represented using key/value pairs provided by the source which do not map to ASim. |
| DstAppId | string | The ID of the destination application, as reported by the reporting device. |
| DstAppName | string | The name of the destination application. |
| DstAppType | string | The type of the destination application. |
| DstBytes | long | The number of bytes sent from the destination to the source for the connection or session. If the event is aggregated, DstBytes is the sum over all aggregated sessions. |
| DstDescription | string | A descriptive text associated with the destination. |
| DstDeviceType | string | The type of the destination device. |
| DstDomain | string | The domain of the destination device. |
| DstDomainType | string | The type of DstDomain. |
| DstDvcId | string | The ID of the destination device. |
| DstDvcIdType | string | The type of DstDvcId. |
| DstFQDN | string | The destination device hostname, including domain information when available. |
| DstGeoCity | string | The city associated with the destination IP address. |
| DstGeoCountry | string | The country associated with the destination IP address. |
| DstGeoLatitude | real | The latitude of the geographical coordinate associated with the destination IP address. |
| DstGeoLongitude | real | The longitude of the geographical coordinate associated with the destination IP address. |
| DstGeoRegion | string | The region, or state, within a country associated with the destination IP address. |
| DstHostname | string | The destination device hostname, excluding domain information. |
| DstInterfaceGuid | string | The GUID of the network interface used on the destination device. |
| DstInterfaceName | string | The network interface used for the connection or session by the destination device. |
| DstIpAddr | string | The IP address of the connection or session destination. |
| DstMacAddr | string | The MAC address of the network interface used for the connection or session by the destination device. |
| DstNatIpAddr | string | The DstNatIpAddr represents either of: The original address of the destination device if network address translation was used or the IP address used by the intermediary device for communication with the source. |
| DstNatPortNumber | int | If reported by an intermediary NAT device, the port used by the NAT device for communication with the source. |
| DstOriginalUserType | string | The original destination user type, if provided by the source. |
| DstPackets | long | The number of packets sent from the destination to the source for the connection or session. The meaning of a packet is defined by the reporting device. If the event is aggregated, DstPackets is the sum over all aggregated sessions. |
| DstPortNumber | int | The destination IP port. |
| DstSubscriptionId | string | The cloud platform subscription ID the destination device belongs to. DstSubscriptionId map to a subscription ID on Azure and to an account ID on AWS. |
| DstUserId | string | A machine-readable, alphanumeric, unique representation of the destination user. |
| DstUserIdType | string | The type of the ID stored in the DstUserId field. |
| DstUsername | string | The destination username, including domain information when available. Use the simple form only if domain information isn't available. |
| DstUsernameType | string | Specifies the type of the username stored in the DstUsername field. |
| DstUserType | string | The type of destination user. |
| DstVlanId | string | The VLAN ID related to the destination device. |
| DstZone | string | The network zone of the destination, as defined by the reporting device. |
| Dvc | string | A unique identifier of the device on which the event occurred or which reported the event. |
| DvcAction | string | The action taken on the network session. |
| DvcDescription | string | A descriptive text associated with the device. For example: Primary Domain Controller. |
| DvcDomain | string | The domain of the device reporting the event. |
| DvcDomainType | string | The type of DvcDomain. Possible values include 'Windows' and 'FQDN'. |
| DvcFQDN | string | The hostname of the device on which the event occurred or which reported the event. |
| DvcHostname | string | The hostname of the device reporting the event. |
| DvcId | string | The unique ID of the device on which the event occurred or which reported the event. |
| DvcIdType | string | The type of DvcId. |
| DvcInboundInterface | string | If reported by an intermediary device, the network interface used by the NAT device for the connection to the source device. |
| DvcInterface | string | The network interface on which data was captured. This field is typically relevant to network related activity which is captured by an intermediate or tap device. |
| DvcIpAddr | string | The IP Address of the device reporting the event. |
| DvcMacAddr | string | The MAC address of the device on which the event occurred or which reported the event. Example: 00:1B:44:11:3A:B7 |
| DvcOriginalAction | string | The original DvcAction as provided by the reporting device. |
| DvcOs | string | The operating system running on the device reporting the event. |
| DvcOsVersion | string | The version of the operating system on the device reporting the event. |
| DvcOutboundInterface | string | If reported by an intermediary device, the network interface used by the NAT device for the connection to the destination device. |
| DvcSubscriptionId | string | The cloud platform subscription ID the device belongs to. DvcSubscriptionId map to a subscription ID on Azure and to an account ID on AWS. |
| DvcZone | string | The network on which the event occurred or which reported the event. The zone is defined by the reporting device. |
| EventCount | int | This value is used when the source supports aggregation, and a single record may represent multiple events. |
| EventEndTime | datetime | The time in which the event ended. If the source supports aggregation and the record represents multiple events, the time that the last event was generated. If not provided by the source record, this field aliases the TimeGenerated field. |
| EventMessage | string | A general message or description. |
| EventOriginalResultDetails | string | The original result details provided by the source. This value is used to derive EventResultDetails, which should have only one of the values documented for each schema. |
| EventOriginalSeverity | string | The original severity as provided by the reporting device. This value is used to derive EventSeverity. |
| EventOriginalSubType | string | The original event subtype or ID, if provided by the source. For example, this field will be used to store the original Windows logon type. This value is used to derive EventSubType, which should have only one of the values documented for each schema. |
| EventOriginalType | string | The original event type or ID, if provided by the source. |
| EventOriginalUid | string | A unique ID of the original record, if provided by the source. |
| EventProduct | string | The product generating the event. |
| EventProductVersion | string | The version of the product generating the event. |
| EventReportUrl | string | A URL provided in the event for a resource that provides more information about the event. |
| EventResult | string | The outcome of the event, represented by one of the following values: Success, Partial, Failure, NA (Not Applicable). The value may not be provided directly by the sources, in which case it is derived from other event fields, for example, the EventResultDetails field. |
| EventResultDetails | string | Reason or details for the result reported in the EventResult field. |
| EventSchemaVersion | string | The version of the schema. |
| EventSeverity | string | The severity of the event. Valid values are: Informational, Low, Medium, or High. |
| EventStartTime | datetime | The time in which the event started. If the source supports aggregation and the record represents multiple events, the time that the first event was generated. If not provided by the source record, this field aliases the TimeGenerated field. |
| EventSubType | string | Additional description of the event type, if applicable. |
| EventType | string | The operation reported by the record. |
| EventVendor | string | The vendor of the product generating the event. |
| NetworkApplicationProtocol | string | The application layer protocol used by the connection or session. |
| NetworkBytes | long | Number of bytes sent in both directions. If both BytesReceived and BytesSent exist, BytesTotal should equal their sum. If the event is aggregated, NetworkBytes is the sum over all aggregated sessions. |
| NetworkConnectionHistory | string | TCP flags and other potential IP header information. |
| NetworkDirection | string | The direction of the connection or session. |
| NetworkDuration | int | The amount of time, in milliseconds, for the completion of the network session or connection. |
| NetworkIcmpCode | int | For an ICMP message, the ICMP message type numeric value as described in RFC 2780 for IPv4 network connections, or in RFC 4443 for IPv6 network connections. |
| NetworkIcmpType | string | For an ICMP message, the ICMP message type text representation, as described in RFC 2780 for IPv4 network connections, or in RFC 4443 for IPv6 network connections. |
| NetworkPackets | long | The number of packets sent in both directions. If both PacketsReceived and PacketsSent exist, BytesTotal should equal their sum. The meaning of a packet is defined by the reporting device. If the event is aggregated, NetworkPackets is the sum over all aggregated sessions. |
| NetworkProtocol | string | The IP protocol used by the connection or session as listed in IANA protocol assignment, which is typically TCP, UDP, or ICMP. |
| NetworkProtocolVersion | string | The version of NetworkProtocol. |
| NetworkRuleName | string | The name or ID of the rule by which DvcAction was decided upon. |
| NetworkRuleNumber | int | The number of the rule by which DvcAction was decided upon. |
| NetworkSessionId | string | The session identifier as reported by the reporting device. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| SrcAppId | string | The ID of the source application, as reported by the reporting device. |
| SrcAppName | string | The name of the source application. |
| SrcAppType | string | The type of the source application. |
| SrcBytes | long | The number of bytes sent from the source to the destination for the connection or session. If the event is aggregated, SrcBytes is the sum over all aggregated sessions. |
| SrcDescription | string | A descriptive text associated with the source. |
| SrcDeviceType | string | The type of the source device. |
| SrcDomain | string | The domain of the source device. |
| SrcDomainType | string | The type of SrcDomain. |
| SrcDvcId | string | The ID of the source device. |
| SrcDvcIdType | string | The type of SrcDvcId. |
| SrcFQDN | string | The source device hostname, including domain information when available. |
| SrcGeoCity | string | The city associated with the source IP address. |
| SrcGeoCountry | string | The country associated with the source IP address. |
| SrcGeoLatitude | real | The latitude of the geographical coordinate associated with the source IP address. |
| SrcGeoLongitude | real | The longitude of the geographical coordinate associated with the source IP address. |
| SrcGeoRegion | string | The region within a country associated with the source IP address. |
| SrcHostname | string | The source device hostname, excluding domain information. If no device name is available, may store the relevant IP address. |
| SrcInterfaceGuid | string | The GUID of the network interface used on the source device. |
| SrcInterfaceName | string | The network interface used for the connection or session by the source device. |
| SrcIpAddr | string | The IP address from which the connection or session originated. |
| SrcMacAddr | string | The MAC address of the network interface from which the connection or session originated. |
| SrcNatIpAddr | string | The SrcNatIpAddr represents either of: The original address of the source device if network address translation was used or the IP address used by the intermediary device for communication with the destination. |
| SrcNatPortNumber | int | If reported by an intermediary NAT device, the port used by the NAT device for communication with the destination. |
| SrcOriginalUserType | string | The original destination user type, if provided by the by the reporting device. |
| SrcPackets | long | The number of packets sent from the source to the destination for the connection or session. The meaning of a packet is defined by the reporting device. If the event is aggregated, SrcPackets is the sum over all aggregated sessions. |
| SrcPortNumber | int | The IP port from which the connection originated. Might not be relevant for a session comprising multiple connections. |
| SrcSubscriptionId | string | The cloud platform subscription ID the source device belongs to. SrcSubscriptionId map to a subscription ID on Azure and to an account ID on AWS. |
| SrcUserId | string | A machine-readable, alphanumeric, unique representation of the source user. |
| SrcUserIdType | string | The type of the ID stored in the SrcUserId field. |
| SrcUsername | string | The source username, including domain information when available. |
| SrcUsernameType | string | Specifies the type of the username stored in the SrcUsername field. |
| SrcUserType | string | The type of the source user. |
| SrcVlanId | string | The VLAN ID related to the source device. |
| SrcZone | string | The network zone of the source, as defined by the reporting device. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TcpFlagsAck | bool | The TCP ACK flag reported. The acknowledgment flag is used to acknowledge the successful receipt of a packet. As we can see from the diagram above, the receiver sends an ACK as well as a SYN in the second step of the three way handshake process to tell the sender that it received its initial packet. |
| TcpFlagsFin | bool | The TCP FIN flag reported. The finished flag means there is no more data from the sender. Therefore, it is used in the last packet sent from the sender. |
| TcpFlagsPsh | bool | The TCP PSH flag reported. The push flag is somewhat similar to the URG flag and tells the receiver to process these packets as they are received instead of buffering them. |
| TcpFlagsRst | bool | The TCP RST flag reported. The reset flag gets sent from the receiver to the sender when a packet is sent to a particular host that was not expecting it. |
| TcpFlagsSyn | bool | The TCP SYN flag reported. The synchronisation flag is used as a first step in establishing a three way handshake between two hosts. Only the first packet from both the sender and receiver should have this flag set. |
| TcpFlagsUrg | bool | The TCP URG flag reported. The urgent flag is used to notify the receiver to process the urgent packets before processing all other packets. The receiver will be notified when all known urgent data has been received. See RFC 6093 for more details. |
| TenantId | string |  |
| ThreatCategory | string | The category of the threat or malware identified in the network session. |
| ThreatConfidence | int | The confidence level of the threat identified, normalized to a value between 0 and a 100. |
| ThreatField | string | The field for which a threat was identified. The value is either SrcIpAddr, DstIpAddr, Domain, or DnsResponseName. |
| ThreatFirstReportedTime | datetime | The first time the IP address or domain were identified as a threat. |
| ThreatId | string | The ID of the threat or malware identified in the network session. |
| ThreatIpAddr | string | An IP address for which a threat was identified. The field ThreatField contains the name of the field ThreatIpAddr represents. |
| ThreatIsActive | bool | True ID the threat identified is considered an active threat. |
| ThreatLastReportedTime | datetime | The last time the IP address or domain were identified as a threat. |
| ThreatName | string | The name of the threat or malware identified in the network session. |
| ThreatOriginalConfidence | string | The original confidence level of the threat identified, as reported by the reporting device. |
| ThreatOriginalRiskLevel | string | The risk level as reported by the reporting device. |
| ThreatRiskLevel | int | The risk level associated with the session. The level is a number between 0 to 100. |
| TimeGenerated | datetime | The timestamp (UTC) reflecting the time in which the event was generated. |
| Type | string | The name of the table |
